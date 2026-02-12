### Generating & Accessing AU Patient Summary (AU PS) Documents
AU PS is specified in this guide as a HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable "minimal" data blocks (the AU PS profiles). See [Structure of the AU PS](the-aups.html#structure-of-the-au-ps).

As in the [IPS Generation and Data Inclusion](https://hl7.org/fhir/uv/ips/Generation-and-Data-Inclusion.html), it is not intended in this release of AU PS IG to constrain solutions or strategies for the creation, sharing and use of AU PS or IPS documents. 

Options for generation and access have been discussed during the AU PS project and HL7 AU Connectathon Track, and the options currently being considered for most implementations in the Australian context are referenced and briefly described in this guide. While the generation operations recommended in the IPS IG are included in this guide, future releases may provide alternative methods and recommendations than those outlined at this time. Some of the potential options for future consideration include: 
* Document Bundle Interactions - FHIR REST API interactions on Bundle resource type to create, update, search and read an IPS document Bundle. A named query search approach could be used to provide more controlled and advanced search requirements.
* Document Bundle and DocumentReference Interactions - Integrating the Healthcare Enterprise (IHE) has published guidance on the [IHE Sharing of IPS (sIPS)](https://profiles.ihe.net/ITI/sIPS/index.html), which has been implemented in a number of jurisdictional implementations of IPS.
* Encrypted File Exchange - in cases where AU PS document exchange is performed using insecure transport media such as email, USB or DVD.


When generating an AU PS document, implementers are advised to be familiar with the following IPS guidance:
- [Narrative and Language Translation](https://hl7.org/fhir/uv/ips/STU2/Design-Conventions.html#narrative-and-language-translation). 
- [Data Included in IPS Documents](https://hl7.org/fhir/uv/ips/STU2/Generation-and-Data-Inclusion.html#data-included-in-ips-documents).

### IPS $summary FHIR Operation
The IPS defines the [IPS Summary](https://hl7.org/fhir/uv/ips/STU2/OperationDefinition-summary.html) (`$summary`) operation and [IPS Server Capability Statement](https://hl7.org/fhir/uv/ips/STU2/CapabilityStatement-ips-server.html), which recommends an IPS Server implement the `$summary` operation as an operation for generating an IPS document.

The `$summary` operation has two endpoint URLs based on the Patient resource:

- `[base]/Patient/$summary` - a Patient resource type endpoint where a patient (business) identifier is provided as a parameter in the operation request body
- `[base]/Patient/[id]/$summary` - a Patient instance endpoint where a patient resource id is provided as a parameter in the URL path

An optional `profile` parameter can be included in the request to allow the server to generate a FHIR document that conforms to the specified profile (e.g. AU PS Composition). If the profile parameter is not provided, or if the specified profile is not supported, the server defaults to generating a document based on the IPS profile.

The `$summary` operation returns a FHIR Bundle resource of type document, containing a Composition resource and its referenced resources. The returned document is typically generated on demand and represents the most current patient summary information. It is not expected that the returned document is persisted as part of this request; therefore, this operation as a standalone does not support use cases where retrieval of a previously generated document is required.

A consuming system can invoke the Patient `$summary` operation on a server to retrieve an on-demand, system generated patient summary. The operation can also be used within a system to generate an initial patient summary document that a user can review, curate, assert, display, persist or take further action on.


<p class="mermaid">
---
config:
  theme: default
---
sequenceDiagram
  participant Server as Patient Summary Server
  participant Consumer as Patient Summary Consumer

  Consumer->>Server: Patient/$summary { identifier, ... } or Patient/[id]/$summary { ... }

  Server-->>Consumer: Bundle { type: 'document' }
</p>
*Figure 1: The IPS Summary operation*
<br/>

### IPA $docref FHIR Operation
The International Patient Access (IPA) defines the [IPA Fetch DocumentReference](https://hl7.org/fhir/uv/ipa/STU1.1/OperationDefinition-docref.html) (`$docref`) operation. FHIR Release 5 has incorporated the Fetch DocumentReference operation as a FHIR operation.

The [IPS Server Capability Statement](https://hl7.org/fhir/uv/ips/STU2/CapabilityStatement-ips-server.html) also recommends the `$docref` operation as an option for an IPS Server to implement generation of an IPS document. It is also worth noting that the [US Core Server CapabilityStatement](https://hl7.org/fhir/us/core/CapabilityStatement-us-core-server.html#documentreference) in Release 8 specifies the $docref operation as SHALL support, although the default patient summary document format is currently a HL7 CDA Continuity of Care Document (CCD). 

The `$docref` operation has a DocumentReference resource type endpoint that returns a searchset Bundle containing DocumentReference resources that match the specified request parameters.

A consuming system can invoke the `$docref` operation on a server to retrieve all DocumentReference resources related to a patient. When no parameters are specified other than the mandatory patient resource id, the server returns a single DocumentReference pointing to the patient’s most current summary document. The type of this summary document depends on jurisdictional processing rules - for example, the Consolidated CDA (C-CDA) is commonly used in North America, whereas in Australia, the document may be specified as an AU PS document.

The `$docref` operation expects that a summary document will always exist or can be dynamically generated. This expectation may be further constrained within a jurisdictional context, including specification of the expected operation outcome when a document is unavailable—such as returning an empty searchset Bundle.

`$docref` operation parameters include:

- `patient`: required patient resource id
- `start`: care date range start
- `end`: care date range end
- `type`: document type codes
- `profile`: document profile URLs
- `on-demand`: only on-demand documents returned

When optional parameters are provided, the server can return existing documents that match the request parameters. In this way, the `$docref` operation behaves similarly to a DocumentReference search. However, if no parameters are provided, a single current summary document is returned. Additionally, if supported, the on-demand parameter allows the client to request generation and storage of a new document.

The document metadata provided in the returned DocumentReference resource can be used to identify a document for retrieval. The `DocumentReference.content.attachment` element is then used to retrieve the referenced document, which may either be encapsulated within the data sub-element or referenced via the url sub-element. A consuming system can retrieve a referenced document by accessing the location specified in the `content.attachment.url` element, which may retrieve a FHIR Binary resource of various document formats.

The `$docref` operation supports multiple document retrieval use cases, including retrieving a patient summary from a previous point in time, accessing the current patient summary, and generating a new document on demand. The benefit of this operation is the use of a single endpoint to support these scenarios, including retrieval of other document types and formats such as HL7 CDA and PDF documents. This flexibility suggests that jurisdictional and implementation-level profiles may be necessary to clearly specify supported input parameters, document capabilities, and the expected output of the operation.


<p class="mermaid">
---
config:
  theme: default
---
sequenceDiagram
  participant Server as Patient Summary Server
  participant Consumer as Patient Summary Consumer
  Consumer->>Server: DocumentReference/$docref { ... }
  Server-->>Consumer: Bundle { type: 'searchset', entry[]: DocumentReference }
  Consumer->>Server: Bundle/[id] read
  Server-->>Consumer: Bundle { type: 'document' }
</p>
*Figure 2: The IPA Fetch DocumentReference operation*
<br/>

### SMART Health Links 
[SMART Health Cards and Links IG](https://hl7.org/fhir/uv/smart-health-cards-and-links/) is an FHIR Standard for Trial Use that supports scenarios where document exchange initiated by the healthcare consumer by sharing a link to a patient summary to trusted recipient.

A user wishing to share an AU PS document retrieves a SMART Health Link (SHL) from an SHL Sharing Application. While the method of retrieving the SHL is not specified by the standard, the SHL itself is a structured, encoded link that includes a URL to a file manifest, an encryption key, and metadata describing the link. It is critical to consider securing the SMART Health Link as it contains the cryptographic key required to access the document. 

The user may optionally specify a passcode, which serves as the only access control mechanism and is required to retrieve the file manifest and subsequently, the patient summary document.

To aid in viewing and processing the patient summary, the SHL can be prefixed with a URL to an SHL Receiving Application, and the complete link can be encoded as a QR code to facilitate sharing.

When the receiving user submits the SHL to an SHL Receiving Application, the application decodes the SHL and, if required, requests a passcode from the receiving user. The decoded data and passcode is used to retrieve a file manifest from the SHL Sharing Application. The manifest contains a list of files - either via external URLs or embedded directly in the response. Once a file is retrieved or decoded, it is decrypted using the key contained in the SHL. The decrypted file contains the patient summary document as a FHIR Bundle resource, which can then be used by the SHL Receiving Application.


<p class="mermaid">
---
config:
  theme: default
---
sequenceDiagram

  participant SharingUser as Sharing User
  participant SharingApp as SHL Sharing Application
  participant ReceivingApp as SHL Receiving Application
  participant ReceivingUser as Receiving User
  SharingUser ->> SharingApp: Create SHL { passcode }
  SharingApp -->> SharingUser: shlink:/ ...
  SharingUser -->> ReceivingUser: Sharing user exchanges SHL with receiving user
  ReceivingUser ->> ReceivingApp: View SHL #shlink:/ ...
  ReceivingApp ->> SharingApp: POST manifest-url { recipient, passcode }
  SharingApp -->> ReceivingApp: Manifest { files: [ { contentType, location | embedded } ]}
  opt 
    ReceivingApp ->> SharingApp: GET location
    SharingApp -->> ReceivingApp: encrypted(Bundle { type: 'document' })
  end
  ReceivingApp ->> ReceivingApp: Decrypt (SHL key)
</p>
*Figure 3: SMART Health Links Patient Summary Exchange*
<br/>

