{::options toc_levels="1..4"/}

<p class="stu-note">The content on this page is intended to address the need for <a href="https://chat.fhir.org/#narrow/channel/207835-IPS/topic/Jurisdictional.20Patient.20Summary.20Specifications">jurisdictional patient summaries</a> to (a) clarify whether they are based on the IPS and if they are (b) make it clear that their IPS summaries are proper IPS and (c) a reference to a section that describes the functional limitations of receiving an IPS document that does not conform to national expectations e.g. what is intended to happen or a possible problem if you are processing IPS documents that don't conform to the national specification.</p>

### The AU PS (AU Patient Summary)

A patient summary is a standardised collection of patient information. Rather than an entire patient health record, it is the minimum necessary and sufficient data to ensure safe patient care. Patient summaries can enhance patient safety by ensuring critical information is readily accessible when it’s needed most and enables clinicians across different health sectors and health domains to provide more informed, consistent care.

The [HL7 International Patient Summary FHIR Implementation Guide](https://hl7.org/fhir/uv/ips/STU2/) (the [IPS](https://hl7.org/fhir/uv/ips/STU2/)) is an internationally recognised patient summary specification that is an implementation of the ISO 27269:2021 Health informatics — International patient summary standard. In 2021, the G7 nations committed to working towards the adoption of the IPS with several international efforts currently underway to drive adoption, including the European Union, USA, Canada and New Zealand. Multinational vendors with presence in Australia are at various stages of implementation of the IPS.

The AU PS will support the consumer on their healthcare journey, providing the consumer and their healthcare providers with timely and current access to relevant health information. It will provide a future pathway for individuals to share their healthcare information when travelling internationally. An AU PS is intended to:
* be an interoperable set of clinical data - it is an electronic health record extract containing essential healthcare information about a consumer
* support individuals on their healthcare journey including transitions of care 
* contain as up to date information as possible based on available sources at a point in time
* be portable and accessible to the individual and their healthcare providers
* be able to be used within an Australian state or territory, across state and territory borders, internationally

<div> 
   <img src="AU-context.png" alt="Context of AU PS across a Consumer's Healthcare Journey" style="width:70%"/>
  </div>
*Figure 1: Context of AU PS across a Consumer's Healthcare Journey in Australia*
<br/>

A sample set of [Consumer Journeys](https://sparked.csiro.au/index.php/products-resources/au-ps-consumer-journeys/), developed by the Sparked AU Patient Summary Clinical Focus Group, help illustrate the interactions and use of a patient summary during a consumer’s healthcare journey in the Australian healthcare context. These Consumer Journeys have been used to develop [two example use cases](usecase.html) to assist implementers in understanding how AU PS could be implemented.

### Structure of the AU PS
AU PS is specified in this guide as an HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable "minimal" data blocks (the AU PS profiles).

Based on [IPS](https://hl7.org/fhir/uv/ips/STU2/) and [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core), AU PS defines a patient summary in the context of providing information to downstream providers. While profiled sections can have content that reflect intentions or orders of clinical care, the patient summary is meant as an informative document and is not intended to be directly actionable. For example, a MedicationRequest resource in the Medication Summary section or a CarePlan resource in the Plan of Care section, is not intended to provide authorisation for fulfilment or actioning from the AU PS (or IPS) document.

The AU PS Document shares the same structure as an IPS, shown below.

 <div> 
    <img src="IPS_composition.png" alt="The IPS composition" style="width:65%"/>
  </div>
*Figure 2: The IPS composition (source: [IPS 2.0.0](https://hl7.org/fhir/uv/ips/STU2//Structure-of-the-International-Patient-Summary.html#structure-of-the-international-patient-summary))*
<br/>

In the AU PS document:
* Required (Mandatory) sections are Problems, Allergies and Intolerances, and Medication Summary
* Recommended sections are Immunizations, Results (Diagnostics), History of Procedures, and Medical Devices
* Optional sections are Advance Directives, Functional Status, History of Pregnancy, Plan of Care, Alerts, History of Past Problems, Patient Story, Social History, and Vital Signs
* Undefined sections are "additional" sections not defined by the AU PS Composition

See the description of each defined section in IPS [Sections description](https://hl7.org/fhir/uv/ips/STU2//Structure-of-the-International-Patient-Summary.html#sections-description).

### Localisation of the IPS

The AU PS is based on [IPS](https://hl7.org/fhir/uv/ips/STU2//) and [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/), allowing for localisations required to meet Australian requirements while still ensuring alignment to the IPS specification:
* A valid AU PS document IS a valid IPS document - the document instance validates against both IGs. 
* A conformant AU PS actor IS a conformant IPS actor - the conformance expectations for implementation for IPS are satisfied when implementing AU PS actor requirements.
* A conformant AU PS actor IS NOT a conformant AU Core actor - AU Core, like IPA, defines actors for FHIR resource access via a RESTful API. AU PS (and IPS) do not define 'access' they define production and consumption of patient summary documents.

<div> 
   <img src="AUPSPassport.png" alt="The AU PS 'Passport'" style="width:25%"/>
  </div>
*Figure 3: The AU PS 'Passport'*
<br/>

While AU PS has no variance (i.e. fully compliant) from IPS Implementation Guide version 2.0.0-ci-build ([current](https://hl7.org/fhir/uv/ips/STU2/)), AU PS does impose requirements additional to IPS to support requirements in the Australian healthcare context (these primarily come from AUCDI and AU Core). These additional requirements are intentionally limited to maximise interoperability with IPS-aware systems. See [Comparison with other national and international IGs](comparison.html) and [Relationship with other IGs](relationship.html) for information on the national and international standards context of AU PS.

Additional requirements for the Australian healthcare context include:
* additionally profiled resources
* additional elements and extensions labelled *Must Support*
* strengthened obligations on some *Must Support* elements
* different and sometimes stronger value set bindings
* strengthened cardinality
* additional fixed values
* additional business rules
* clarified expectations for missing data, empty sections, and suppressed data

A summary of these additional requirements is provided in the sections below. While every effort has been made to ensure this page is consistent with the requirements of AU PS this is not a normative part of the specification.

#### Additionally Profiled Resources

AU PS profiles the following resources that are not profiled in IPS:

- [AU PS Encounter](StructureDefinition-au-ps-encounter.html) profiles FHIR resource [Encounter](http://hl7.org/fhir/R4/encounter.html)
- [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html) profiles FHIR resource [RelatedPerson](http://hl7.org/fhir/R4/relatedperson.html)

In addition to the profiles defined in this implementation guide and in IPS, the following profiles defined elsewhere are used by AU PS as the target of a *Must Support* reference element in an AU PS profile:
- [AU Core Location](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-location.html)
- AU Core localised Vital Signs profiles (with additional cardinality and fixed value constraints)
  - [AU Core Blood Pressure](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bloodpressure.html)
  - [AU Core Body Height](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodyheight.html)
  - [AU Core Body Temperature](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodytemp.html)
  - [AU Core Body Weight](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodyweight.html)
  - [AU Core Heart Rate](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-heartrate.html)
  - [AU Core Respiration Rate](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-resprate.html)
  - [AU Core Waist Circumference](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-waistcircum.html)

#### Must Support Extensions
No extensions are labelled as *Must Support* in IPS. In AU PS, the following extensions are labelled as *Must Support*:
* [Australian Indigenous Status](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-indigenous-status.html) in [AU PS Patient](StructureDefinition-au-ps-patient.html)
* [Individual Pronouns](https://hl7.org/fhir/extensions/5.1.0/StructureDefinition-individual-pronouns.html) in [AU PS Patient](StructureDefinition-au-ps-patient.html)
* [Individual Gender Identity](https://hl7.org/fhir/extensions/5.1.0/StructureDefinition-individual-genderIdentity.html) in [AU PS Patient](StructureDefinition-au-ps-patient.html)

#### Terminology
 A full list of terminology differences is not provided, refer to the [AU PS profiles](profiles-and-extensions.html) and the [Terminology](terminology.html) page to understand the terminology supported for use in AU PS. Some differences are mentioned below to highlight their potential relevance to implementers of the AU PS.

AU PS:
* adopts terminology bound in AU Core in preference to IPS where the IPS binding strength is equivalent or weaker.
* localised terminology bindings are present in the additionally profiled resources and *Must Support* extensions.
* defines support for more multiple terminologies for medicines and vaccines, see the table in the section [Must Support - Choice of Terminology](general-requirements.html#must-support---choice-of-terminology).
* applies a stronger binding strength (e.g. preferred -> extensible) for some *Must Support* elements (the binding strength is inherited from AU Core).
 
In many cases the difference between value sets bound in AU Core and IPS is the IPS use of international SNOMED CT concepts versus the AU Core use of SNOMED CT-AU concepts and international SNOMED CT concepts. Typically these Australian value sets are bound as [preferred](https://hl7.org/fhir/R4/terminologies.html#extensible) in AU PS profiles; these are recommendations for use in the Australian healthcare context but do not prevent other coding or text only representations. 

#### Cardinality
While AU PS profiles do not apply unique maximum cardinality constraints, AU PS makes a number of elements mandatory (minimum cardinality > 0) that are not mandatory in IPS either directly in the AU PS profile or by reference to an AU Core profile. These constrained cardinalities are typically in:
- additionally profiled resource types that mandate reference to the patient.
- simple observation profiles (e.g. body temperature or smoking status) that require either a value or a data absent reason.
- profiles of individuals and entities (e.g. Location, Patient, RelatedPerson, PractitionerRole, Practitioner) that have additional mandatory administrative elements e.g. Patient.identifier or PractitionerRole.practitioner.

#### Identifiers
IPS does not provide recommendations on the types of identifiers used in resources, this is expected to be defined as needed in jurisdictional specifications. In AU PS, a number of optional national Australian healthcare identifiers are labelled with *Must Support*, see the table in the section [Must Support - Choice of Identifiers](general-requirements.html#must-support---choice-of-identifiers) for the full list.

#### Fixed Values
AU PS includes additional fixed value constraints on some elements either directly in an AU PS profile or via reference to an AU Core profile. These additional fixed values are typically in Observation profiles and add a fixed SNOMED CT concept in `Observation.code` in addition to the fixed LOINC code. 

### Considerations When Consuming IPS Documents in AU Healthcare Context

<p class="request-for-feedback">Implementers are requested to contribute to identification of the functional limitations of receiving an IPS document that does not conform to national expectations, e.g. does not include Australian identifiers, does not include clinical terminology from a national set (see specific localisations listed above), does not include mandatory elements. Contribute via comment on <a href="https://jira.hl7.org/browse/FHIR-51547">FHIR-51547</a>.</p>
