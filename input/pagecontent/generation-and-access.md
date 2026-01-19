### Generating & Accessing AU Patient Summary (AU PS) Documents
AU PS is specified in this guide as a HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable "minimal" data blocks (the AU PS profiles). See [Structure of the AU PS](the-aups.html#structure-of-the-au-ps).

As in the IPS, it is not in the scope of this version of AU PS to constrain solutions or strategies for the creation, sharing, translation, and use of AU PS Documents or IPS Documents. 

Options for access and exchange that have been discussed during AU PS meetings are briefly described in this guide with links to their source specifications. While recommendations on operations from IPS on generation are included in this guide, future implementation guides may provide alternative methods and further recommendations different than those outlined. In addition, Integrating the Healthcare Enterprise (IHE) has also published guidance on the [IHE Sharing of IPS (sIPS)](https://profiles.ihe.net/ITI/sIPS/index.html) which may be a helpful reference.

When generating an AU PS Document, implementers are also advised to be familiar with the following IPS guidance:
- [Narrative and Language Translation](https://hl7.org/fhir/uv/ips/STU2/Design-Conventions.html#narrative-and-language-translation). 
- [Data Included in IPS Documents](https://hl7.org/fhir/uv/ips/STU2/Generation-and-Data-Inclusion.html#data-included-in-ips-documents).

### IPS $summary FHIR Operation
The IPS defines the [IPS Summary](https://hl7.org/fhir/uv/ips/STU2/OperationDefinition-summary.html) (`$summary`) operation and [IPS Server Capability Statement](https://hl7.org/fhir/uv/ips/STU2/CapabilityStatement-ips-server.html), which recommends an IPS Server implement the `$summary` operation as an operation for generating an IPS Document.

The `$summary` operation has two endpoint URLs based on the Patient resource:

- `[base]/Patient/$summary` - a Patient resource type endpoint where a patient (business) identifier is provided as a parameter in the operation request body
- `[base]/Patient/[id]/$summary` - a Patient instance endpoint where a patient resource id is provided as a parameter in the URL path

An optional `profile` parameter can be included in the request to allow the server to generate a FHIR Document that conforms to the specified profile (e.g. AU PS Composition). If the profile parameter is not provided, or if the specified profile is not supported, the server defaults to generating a document based on the IPS profile.

The `$summary` operation returns a FHIR Bundle resource of type document, containing a Composition resource and its referenced resources. The returned document is typically generated on demand and represents the most current patient summary information. It is not expected that the returned document is persisted as part of this request; therefore, this operation as a standalone does not support use cases where retrieval of a previously generated document is required.

A consuming system can invoke the Patient `$summary` operation on a server to retrieve an on-demand, system generated patient summary. The operation can also be used internally within a system to generate an initial patient summary document that a user can review, curate, assert, display, persist or take further action on.

<div> 
  <img src="ga-summaryoperation.png" alt="IPS Summary Operation" style="width:60%"/>
</div>
*Figure 1: The IPS Summary operation*
<br/>

### IPA $docref FHIR Operation
The International Patient Access (IPA) defines the [IPA Fetch DocumentReference](https://hl7.org/fhir/uv/ipa/STU1.1/OperationDefinition-docref.html) (`$docref`) operation. FHIR Release 5 has incorporated the Fetch DocumentReference operation as a FHIR operation.

The [IPS Server Capability Statement](https://hl7.org/fhir/uv/ips/STU2/CapabilityStatement-ips-server.html) identifies the `$docref` operation as an option for an IPS Server to implement for generating an IPS document.

The `$docref` operation has a DocumentReference resource type endpoint that returns a searchset Bundle containing DocumentReference resources that match the specified request parameters.

A consuming system can invoke the `$docref` operation on a server to retrieve all DocumentReference resources related to a patient. When no parameters are specified other than the mandatory patient resource id, the server returns a single DocumentReference pointing to the patient’s most current summary document. The type of this summary document depends on jurisdictional processing rules - for example, the Consolidated CDA (C-CDA) is commonly used in North America, whereas in Australia, the document may be specified as an AU PS Document .

The `$docref` operation expects that a summary document will always exist or can be dynamically generated. This expectation may be further constrained within a jurisdictional context, including specification of the expected operation outcome when a document is unavailable—such as returning an empty searchset Bundle.

`$docref` operation parameters include:

- `patient`: required patient resource id
- `start`: care date range start
- `end`: care date range end
- `type`: document type codes
- `profile`: document profile URLs
- `on-demand`: only on-demand documents returned

When optional parameters are provided, the server can return existing documents that match the request parameters. In this way, the `$docref` operation behaves similarly to a DocumentReference search. However, if no parameters are provided, a single current summary document is returned. Additionally, if supported, the on-demand parameter allows the client to request generation and storage of a new document.

The document metadata provided in the returned DocumentReference resource can be used to identify a document for retrieval. The `DocumentReference.content.attachment` element is then used to retrieve the referenced document, which may either be encapsulated within the data sub-element or referenced via the url sub-element. A consuming system can retrieve a referenced document Bundle using the FHIR RESTful Bundle read interaction. Other document formats can be retrieved by accessing the location specified in the `content.attachment.url` element, which may point to a FHIR Binary resource.

The `$docref` operation supports multiple document retrieval use cases, including retrieving a patient summary from a previous point in time, accessing the current patient summary, and generating a new document on demand. The benefit of this operation is the use of a single endpoint to support these scenarios, including retrieval of other document types and formats such as HL7 CDA and PDF documents. This flexibility suggests that jurisdictional and implementation-level profiles may be necessary to clearly specify supported input parameters, document capabilities, and the expected output behaviour of the operation.

<div> 
  <img src="ga-docrefoperation.png" alt="IPA Fetch DocumentReference Operation" style="width:60%"/>
</div>
*Figure 2: The IPA Fetch DocumentReference operation*
<br/>

### Document Bundle Interactions
As the AU PS is a FHIR Bundle of type document, implementers can leverage standard FHIR REST API interactions. The document Bundle (AU PS Document) can be stored, discovered and retrieved using the REST interactions `Bundle create`, `search` and `read` interactions.

The `search` and `read` interactions support the scenarios where an AU PS Producer stores the AU PS Document within their system and provides access to a consuming system.

The `create` interaction supports scenarios when an AU PS Producer stores the AU PS Document in a separate patient summary server. A consuming system can then access the AU PS Document using the `search` and `read` interactions.

Alternatively, an AU PS Producer can choose to upload the AU PS Document directly to a consuming system using the `create` interaction, enabling the consuming system to process or view the AU PS Document.

<div> 
  <img src="ga-bundleinteractions.png" alt="Document Bundle Interactions" style="width:80%"/>
</div>
*Figure 3: Document Bundle Interactions*
<br/>

### Named Bundle Search Interaction
A variation of the Bundle search interaction is the use of [named query](https://hl7.org/fhir/R5/search.html#advanced) parameters. This approach supports advanced querying scenarios that require specific or complex parameters and processing logic. Named query profiles and parameters are defined using the `OperationDefinition` resource. These named search interactions are invoked on a resource-type or system-wide endpoint by using the `_query` parameter to specify the query name.

Using a named `_query` parameter in a Bundle search interaction can support common search criteria across multiple patient summary use cases. However, it is not intended to support on-demand generation of AU PS Documents. The use of named queries necessitates implementer profiling and custom implementation in both requesting and responding systems.

### Document Bundle and DocumentReference Interactions
The FHIR DocumentReference resource provides a generalised method for indexing clinical documents within an electronic medical record system, irrespective of the document’s media type or format. For an AU PS Document, this approach requires that both the AU PS Document (Bundle) and its associated metadata (a DocumentReference resource linking to the document) are stored in a consistent, discoverable manner.

To ensure data integrity and reliability, an AU PS Producer can include the AU PS Document Bundle within a FHIR transaction Bundle, specifying the request as a create interaction. A DocumentReference resource, populated with metadata extracted from the AU PS Document Bundle and its Composition resource, along with a reference to the AU PS Document Bundle, is also included in the transaction as a create interaction request. This transaction Bundle is POSTed to the whole-system ([baseUrl]) endpoint of a server, which ensures that both create operations succeed or fail together.

A consuming system can discover an AU PS Document using a DocumentReference search interaction, with query parameters based on metadata extracted from the Bundle and Composition resources. The response is a searchset Bundle containing matching DocumentReference resources.

The consuming system can then retrieve a specific AU PS Document Bundle from the server by using the value in the `content.attachment.url` element of the selected DocumentReference.

In systems where AU PS Documents are generated and stored internally, the DocumentReference search and Bundle read interactions can be used by a consuming system to discover and retrieve documents as described above.

<div> 
  <img src="ga-bundledocrefinteractions.png" alt="Document Bundle and Document Reference Interactions" style="width:80%"/>
</div>
*Figure 4: Document Bundle and Document Reference Interactions*
<br/>

### IHE MHD Provide Document Bundle 
The DocumentReference and document Bundle transaction represents a simplified profile of the [IHE MHD Provide Document Bundle [ITI-65]](https://profiles.ihe.net/ITI/MHD/ITI-65.html) transaction. The full ITI-65 specification also requires a List resource that provides document set metadata for all documents included in the transaction. This supports IHE Cross-enterprise Document Sharing (XDS) repository implementations where multiple documents or document attachments are submitted to a document store in a single transaction.

While this approach is well-suited to technical implementations based on XDS repositories, it requires the AU PS Producer to also generate the additional metadata resources - even though there is usually only a single document being provided in the transaction.

### IHE MHD Simplified Publish
IHE provides an optional transaction profile, [Simplified Publish [ITI-105]](https://profiles.ihe.net/ITI/MHD/ITI-105.html). This transaction allows an AU PS Producer to create a DocumentReference resource containing a document Bundle instance that is base64-encoded and populated in `DocumentReference.content.attachment.data`. It is the responsibility of the AU PS Producer to ensure that the metadata in the DocumentReference resource is populated in a way that supports document discovery via search.

The server accepts the DocumentReference resource, extracts and decodes the document Bundle from `DocumentReference.content.attachment.data`, and persists the resulting Bundle resource. A reference to the Bundle is then populated in `DocumentReference.content.attachment.url`, replacing the original `attachment.data` element, and the updated DocumentReference is persisted.

When the DocumentReference is included in the response to a DocumentReference create interaction, the persisted version is returned, containing the `DocumentReference.content.attachment.url`. Similarly, any search responses that include the DocumentReference will contain the `attachment.url`, and a Bundle read interaction will be required to retrieve the AU PS Document.

<div> 
  <img src="ga-mhdsimplifiedpublish.png" alt="IHE MHD Simplified Publish" style="width:100%"/>
</div>
*Figure 5: IHE MHD Simplified Publish*
<br/>

### Encrypted File Exchange
There are scenarios where AU PS Document exchange cannot be performed using a FHIR API, and trusted user authentication is not available. In such cases, it is necessary to ensure the secure exchange of AU PS Documents as files, particularly when using insecure media such as email, USB, or DVD.

Public Key Infrastructure (PKI) is a well-established approach to ensure end-to-end security by encrypting the AU PS Document file using the public key of the intended recipient. Once delivered, the recipient can decrypt the file using their private key. The decrypted file can then be uploaded into the consuming system for processing.

<div> 
  <img src="ga-encryptedfileexchange.png" alt="Encrypted File Exchange" style="width:60%"/>
</div>
*Figure 6: Encrypted file exchange*
<br/>

### SMART Health Links 
[SMART Health Cards and Links IG](https://build.fhir.org/ig/HL7/smart-health-cards-and-links/) is an in-progress FHIR Implementation Guide that supports scenarios where document exchange cannot be performed using a FHIR API, and the identity of the recipient is unknown. It enables a patient or another trusted party to share a link to the document instead.

It is critical to consider how to secure the SMART Health Link itself, as it contains the cryptographic key required to access the document.

A user wishing to share an AU PS Document retrieves a SMART Health Link (SHL) from an SHL Sharing Application. While the method of retrieving the SHL is not specified by the standard, the SHL itself is a structured, encoded link that includes a URL to a file manifest, an encryption key, and metadata describing the link.

The user may optionally specify a passcode, which serves as the only access control mechanism and is required to retrieve the file manifest and, ultimately, the AU PS Document.

To aid in exchange, the SHL can be prefixed with a URL to an SHL Receiving Application, and the complete link can be encoded as a QR code for scanning.

When the receiving user submits the SHL to an SHL Receiving Application, the application decodes the SHL and, if required, accepts the passcode provided by the Sharing User. The decoded data and passcode are then used to retrieve the file manifest from the SHL Sharing Application. The manifest contains a list of files - either via external URLs or embedded directly in the response. Once a file is retrieved or decoded, it is decrypted using the key contained in the SHL. The decrypted file contains the AU PS Document as a FHIR Bundle resource, which can then be processed by the SHL Receiving Application.
<div> 
  <img src="ga-smarthealthlinks.png" alt="SMART Health Links Patient Summary Exchange" style="width:100%"/>
</div>
*Figure 7: SMART Health Links Patient Summary Exchange*
<br/>

