{::options toc_levels="1..4"/}

<p class="stu-note">The content on this page is intended to address the need for <a href="https://chat.fhir.org/#narrow/channel/207835-IPS/topic/Jurisdictional.20Patient.20Summary.20Specifications">jurisdictional patient summaries</a> to (a) clarify whether they are based on the IPS and if they are (b) make it clear that their IPS summaries are proper IPS and (c) a reference to a section that describes the functional limitations of receiving an IPS document that does not conform to national expectations e.g. what is intended to happen or a possible problem if you are processing IPS documents that don't conform to the national specification.</p>

### The AU PS (AU Patient Summary)

A patient summary is a standardised collection of patient information. Rather than an entire patient health record, it is the necessary minimum and sufficient data to ensure safe patient care. Patient summaries can enhance patient safety by ensuring critical information is readily accessible when it’s needed most and enables clinicians across different health sectors and health domains to provide more informed, consistent care.

The [IPS](https://build.fhir.org/ig/HL7/fhir-ips) is a globally recognised patient summary standard. In 2021, the G7 nations committed to working towards the adoption of the IPS with several international efforts being currently underway to drive adoption, including the European Union, USA, Canada and New Zealand. Multinational vendors with presence in Australia are at various stages of implementation of the IPS.

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
AU PS is specified in this guide as a HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable "minimal" data blocks (the AU PS profiles).

Based on IPS and AU Core, AU PS defines a patient summary in the context of providing information to downstream providers. While profiled sections can have content that reflect intentions or orders of clinical care, the patient summary is meant as an informative document and is not intended to be directly actionable. For example, a MedicationRequest resource in the Medication Summary section or a CarePlan resource in the Plan of Care section, is not intended to provide authorisation for fulfilment or actioning from the AU PS (or IPS) document.

The AU PS Document shares the same structure as an IPS, shown below.

 <div> 
    <img src="IPS_composition.png" alt="The IPS composition" style="width:65%"/>
  </div>
*Figure 2: The IPS composition (source: [IPS 2.0.0](https://build.fhir.org/ig/HL7/fhir-ips/Structure-of-the-International-Patient-Summary.html#structure-of-the-international-patient-summary))*
<br/>

In the AU PS document:
* Required (Mandatory) sections are Problems, Allergies and Intolerances, and Medication Summary
* Recommended sections are Immunizations, Results (Diagnostics), History of Procedures, and Medical Devices
* Optional sections are Advance Directives, Functional Status, History of Pregnancy, Plan of Care, Alerts, History of Past Problems, Patient Story, Social History, and Vital Signs
* Undefined sections are "additional" sections not defined by the AU PS Composition

See the description of each defined section in IPS [Sections description](https://build.fhir.org/ig/HL7/fhir-ips/Structure-of-the-International-Patient-Summary.html#sections-description).

### Localisation of the IPS

The AU PS is based on [IPS](https://build.fhir.org/ig/HL7/fhir-ips/) and [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/), allowing for localisations required to meet Australian requirements while still ensuring alignment to the IPS specification:
* A valid AU PS document IS a valid IPS document - the document instance validates against both IGs (and against AU Core profiles). 
* A conformant AU PS actor IS a conformant IPS actor (the conformance expectations for implementation for IPS are satisfied when implementing AU PS actor requirements).
* A conformant AU PS actor IS NOT a conformant AU Core actor. AU Core, like IPA, defines actors for FHIR resource access via a RESTful API, AU PS (and IPS) do not define 'access' they define production and consumption of patient summary documents.

<div> 
   <img src="AUPSPassport.png" alt="The AU PS 'Passport'" style="width:25%"/>
  </div>
*Figure 3: The AU PS 'Passport'*
<br/>

While AU PS has no variance (i.e. fully compliant) from IPS Implementation Guide version 2.0.0-ci-build ([current](https://build.fhir.org/ig/HL7/fhir-ips)), AU PS does impose requirements additional to IPS to support requirements in the Australian healthcare context (these primarily come from AUCDI and AU Core). These additional requirements are intentionally limited to maximise interopability with IPS-aware systems. See [Comparison with other national and international IGs](comparison.html) and [Relationship with other IGs](relationship.html) for information on the national and international standards context of AU PS.

Additional requirements include:
* additionally profiled resources
* additional elements marked as *Must Support*
* strengthened obligations on some *Must Support* elements
* different value set bindings
* strengthened cardinality
* additional fixed values
* additional business rules
* clarified expectations for missing data, empty sections, and suppressed data

A summary of differences is provided in the sections below. While every effort has been made to ensure this page is consistent with the requirements of AU PS this is not a normative part of the specification.


#### Additionally Profiled Resources

AU PS profiles the following resources that are not profiled in IPS:

- [AU PS Encounter](StructureDefinition-au-ps-encounter.html) profiles FHIR resource [Encounter](http://hl7.org/fhir/R4/encounter.html)
- [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html) profiles FHIR resource [RelatedPerson](http://hl7.org/fhir/R4/relatedperson.html)
- [AU Core Waist Circumference](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-waistcircum.html) profiles FHIR profile [VitalSigns](https://hl7.org/fhir/R4/vitalsigns.html)

In addition to the profiles defined in this implementation guide and in IPS, the following profiles defined elsewhere are used by AU PS as the target of a *Must Support* reference element in an AU PS profile:
- [AU Core Location](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-location.html)

#### Must Support Extensions
No extensions are labelled as *Must Support* in IPS. In AU PS the following extensions are labelled as *Must Support*:
* [Australian Indigenous Status](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-indigenous-status.html) in [AU PS Patient](StructureDefinition-au-ps-patient.html)
* [Individual Pronouns](https://hl7.org/fhir/extensions/5.1.0/StructureDefinition-individual-pronouns.html) in [AU PS Patient](StructureDefinition-au-ps-patient.html)
* [Individual Gender Identity](https://hl7.org/fhir/extensions/5.1.0/StructureDefinition-individual-genderIdentity.html) in [AU PS Patient](StructureDefinition-au-ps-patient.html)

#### Terminology
AU PS adopts the clinical terminology defined in AU Core in preference to IPS where the IPS binding strength is equivalent or weaker. 

In many cases the difference between value sets is the IPS use of international SNOMED CT concepts versus the AU Core use of international SNOMED CT and SNOMED CT-AU concepts. For these sets the binding strength in specifications is [preferred](https://hl7.org/fhir/R4/terminologies.html#extensible); these are recommendations for use in the Australian healthcare context but do not prevent other coding or text only representations. A list of terminology differences is not provided on this page, refer to the AU PS profiles to understand the terminology recommended for use in AU PS.

In AU PS, some elements define support for more than one value set, for this list and how producers and consumers are to interpret support, see the table in the section [Must Support - Choice of Terminology](general-requirements.html#must-support---choice-of-terminology).

For a limited set of elements, the terminology constraint in AU PS (or referenced profile) is stronger than IPS, see the table below:

Profile |Element
---|---
[AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)|AllergyIntolerance.code - AU PS Binding: [Indicator of Hypersensitivity or Intolerance to Substance](https://healthterminologies.gov.au/fhir/ValueSet/indicator-hypersensitivity-intolerance-to-substance-2) (extensible)
[AU Core Blood Pressure](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bloodpressure.html)|Observation.bodySite - If a coded body site is provided, at least one coding shall be from SNOMED CT (au-core-obs-02)
[AU Core Body Height](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodyheight.html)|Observation.bodySite - If a coded body site is provided, at least one coding shall be from SNOMED CT (au-core-obs-02)
[AU Core Body Temperature](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodytemp.html)|Observation.bodySite - If a coded body site is provided, at least one coding shall be from SNOMED CT (au-core-obs-02)
[AU Core Body Weight](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodyweight.html)|Observation.bodySite - If a coded body site is provided, at least one coding shall be from SNOMED CT (au-core-obs-02)
[AU PS Condition](StructureDefinition-au-ps-condition.html)|Condition.severity - AU PS Binding: [Condition/Diagnosis Severity](https://hl7.org/fhir/R4/valueset-condition-severity.html) (extensible)
[AU PS Condition](StructureDefinition-au-ps-condition.html)|Condition.code - AU PS Binding: [Clinical Condition](https://healthterminologies.gov.au/fhir/ValueSet/clinical-condition-1) (extensible)
[AU PS Condition](StructureDefinition-au-ps-condition.html)|Condition.bodySite - AU PS Binding: [Body Site](https://healthterminologies.gov.au/fhir/ValueSet/body-site-1) (extensible)
[AU Core Heart Rate](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-heartrate.html)|Observation.bodySite - If a coded body site is provided, at least one coding shall be from SNOMED CT (au-core-obs-02)
[AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)|Observation.code - AU PS Binding: [RCPA SPIA Pathology Reporting](https://healthterminologies.gov.au/fhir/ValueSet/spia-pathology-reporting-1) (extensible)
[AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)|Observation.component.code - AU PS Binding: [RCPA SPIA Pathology Reporting](https://healthterminologies.gov.au/fhir/ValueSet/spia-pathology-reporting-1) (extensible)
[AU PS Patient](StructureDefinition-au-ps-patient.html)|Patient.extension:genderIdentity - AU PS Binding: Gender identity shall be a member of the Gender Identity Response value set if any codes within that value set can apply (inv-pat-1)
[AU PS Patient](StructureDefinition-au-ps-patient.html)|Patient.extension:individualPronouns - Pronouns shall be a member of the Australian Pronouns value set if any codes within that value set can apply (inv-pat-2	)
[AU PS Patient](StructureDefinition-au-ps-patient.html)|Patient.communication.language - AU PS Binding: [Common Languages in Australia](https://healthterminologies.gov.au/fhir/ValueSet/common-languages-australia-2) (extensible)
[AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html)|RelatedPerson.relationship - AU PS Binding: [Related Person Relationship Type](https://healthterminologies.gov.au/fhir/ValueSet/related-person-relationship-type-1) (extensible)
[AU Core Respiration Rate](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-resprate.html)|Observation.bodySite - If a coded body site is provided, at least one coding shall be from SNOMED CT (au-core-obs-02)
[AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.html)|Observation.value - AU PS Binding: [Smoking Status](https://healthterminologies.gov.au/fhir/ValueSet/smoking-status-1) (extensible)
[AU Core Waist Circumference](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-waistcircum.html)|Observation.bodySite - If a coded body site is provided, at least one coding shall be from SNOMED CT (au-core-obs-02)
{:.grid}


#### Cardinality
While AU PS does not apply any unique maximum cardinality constraints, AU PS makes a number of elements mandatory (minimum cardinality > 0) that are not mandatory in IPS, see the tables below.

Profile |Mandatory Element defined in AU PS
---|---
[AU PS Condition](StructureDefinition-au-ps-condition.html)|Condition.category
[AU PS Encounter](StructureDefinition-au-ps-encounter.html)|Encounter.subject
[AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)|MedicationRequest.authoredOn, MedicationRequest.requester
[AU PS Patient](StructureDefinition-au-ps-patient.html)|Patient.identifier, Patient.gender
[AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)|Practitioner.name.family
[AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.html)|PractitionerRole.practitioner
[AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html)|RelatedPerson.patient
{:.grid}

Profile |Conditionally Mandatory Element defined in AU PS
---|---
[AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.html)|Observation.value OR Observation.dataAbsentReason is required (au-core-obs-01)
[AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html)|RelatedPerson.name OR RelatedPerson.relationship is required (au-core-relper-01)
[AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.html)|Observation.value OR Observation.dataAbsentReason is required (au-core-obs-01)
{:.grid}

#### Identifiers
IPS does not provide recommendations on the types of identifiers used in resources, this is expected to be defined as needed in jurisdictional specifications. In AU PS, a number of optional national Australian healthcare identifiers are labelled with *Must Support*, see the table in the section [Must Support - Choice of Identifiers](general-requirements.html#must-support---choice-of-identifiers) for the full list and to interpret the support requirements for producers and consumers.

#### Fixed Values
AU PS includes additional fixed value constraints to some elements in profiles either directly in an AU PS profile or via reference to an AU Core profile. These additional fixed values are typically in Observation profiles and add a fixed SNOMED CT concept in `Observation.code` in addition to the LOINC code. See the table below:

Profile |Element|Additional fixed value
---|---|---
[AU Core Blood Pressure](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bloodpressure.html)|Observation.code|SNOMED CT code 75367002\|Blood pressure\|
[AU Core Body Height](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodyheight.html)|Observation.code|SNOMED CT code 50373000\|Body height measure\|
[AU Core Body Temperature](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodytemp.html)|Observation.code|SNOMED CT code 386725007\|Body temperature\|
[AU Core Body Weight](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-bodyweight.html)|Observation.code|SNOMED CT code 27113001\|Body weight\|
[AU Core Heart Rate](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-heartrate.html)|Observation.code|SNOMED CT code 364075005\|Heart rate\|
[AU Core Respiration Rate](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-resprate.html)|Observation.code|SNOMED CT code 86290005\|Respiratory rate\|
[AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.html)|Observation.code|SNOMED CT code 1747861000168109\|Smoking status\|
{:.grid}

### Considerations When Consuming IPS Documents in AU Healthcare Context

<p class="request-for-feedback">Implementers are requested to contribute via comment on <a href="https://jira.hl7.org/browse/FHIR-51547">FHIR-51547</a> the functional limitations of receiving an IPS document that does not conform to national expectations e.g. does not include Australian identifiers, does not include clinical terminology from a national set (see specific localisations listed above), does not include mandatory elements.</p>
