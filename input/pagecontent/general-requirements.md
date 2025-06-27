### Conforming to AU PS

Systems claiming conformance to AU Patient Summary will represent digital health information using the content models of AU Patient Summary profiles AND implement the requirements for one or both [AU PS actors](actors.html).

The requirements of the FHIR standard and [FHIR Conformance Rules](http://hl7.org/fhir/conformance-rules.html) apply, and define the use of terms in this guide including the conformance verbs - **SHALL**, **SHALL NOT**, **SHOULD**, **SHOULD NOT**, **MAY**.

Implementers are advised to be familiar with the requirements of the FHIR standard and IPS when implementing AU PS, in particular:
- [IPS Generation and Data Inclusion](https://build.fhir.org/ig/HL7/fhir-ips/Generation-and-Data-Inclusion.html#generation-and-data-inclusion)
- [IPS Narrative and Language Translation](https://build.fhir.org/ig/HL7/fhir-ips/Design-Conventions.html#narrative-and-language-translation)
- [FHIR Terminology requirements](http://hl7.org/fhir/R4/terminologies.html)
- [FHIR Documents](https://hl7.org/fhir/R4/documents.html) 
- [FHIR RESTful API](http://hl7.org/fhir/R4/http.html) 
- [FHIR Search](http://hl7.org/fhir/R4/search.html)
- [FHIR Resource formats](http://hl7.org/fhir/R4/resource.html)
- [FHIR Data Types](http://hl7.org/fhir/R4/datatypes.html)

### Conformance Artifacts

#### AU PS Profiles and Extensions
The [Profiles and Extensions](profiles-and-extensions.html) page lists the AU PS profiles and extensions defined for this implementation guide. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the minimum elements, extensions, vocabularies and value sets that **SHALL** be present and constrains the way elements are used when conforming to the profile.

AU PS profile elements include mandatory and *Must Support* requirements. [Mandatory elements](#mandatory-elements) are required and have a minimum cardinality of 1 (min=1). [Must Support](#must-support-and-obligation) elements have defined conformance obligations in AU PS.

#### AU PS Actors
The [Actor Definitions](actors.html) page lists the AU PS actors defined for this implementation guide and the requirements for implementing that actor. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the obligations for an AU PS actor when implementing that profile.

### Mandatory Elements
Mandatory elements are elements with minimum cardinality > 0. When an element is mandatory, the data is expected to always be present. Very rarely, it may not be, and in this circumstance the requirements defined by AU Core for [Missing Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-data) **SHALL** be applied. 

An element can be both *Must Support* and mandatory, in which case the requirements defined by AU Core for mandatory's Missing Data requirements **SHALL** be applied as described in [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data).

The convention in this guide is to mark all mandatory and conditionally mandatory elements as *Must Support* unless they are nested under an optional element.

### Missing Data and Empty Sections

There are situations when information is missing, this could be at the section level where a source system does not have information on a patient's medical devices, or may be at an element level within a resource. 

Where data is missing for an element within a resource and the reason is not known, systems **SHALL** implement the requirements of the [Missing Data](general-requirements.html#missing-data) section.

Where data is missing at the section level and the reason is not known, systems **SHALL** implement the requirements of the [Empty Sections](general-requirements.html#empty-sections) section.

<div class="stu-note" markdown="1">
It is proposed that missing data is distinct from a known absence of data for either:
* no known x - where it is known, for example, that there are no known allergies for a patient
* workflow - where there is a known workflow reason information for the section is not available

See the proposal AU PS Conformance Proposal: <a href="https://build.fhir.org/ig/hl7au/au-fhir-ps/branches/ft_conf-proposal/general-requirements.html">Narrative conformance requirements</a> e.g. Missing Data, Empty Sections</li>.

This proposal will be voted on in next AU PS FHIR IG Call this Friday: <a href="https://confluence.hl7.org/spaces/HAFWG/pages/358878850/2025-07-11+AU+Patient+Summary+FHIR+IG+Agenda+Minutes">2025-07-11 AU Patient Summary FHIR IG Agenda/Minutes</a>.
</div><!-- stu-note -->

#### Missing Data

##### Missing Must Support and Optional Data

If the source system (producer) does not know the value for an optional element (minimum cardinality = 0), including elements labelled *Must Support*, as per the requirements defined in [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-optional-data), the data element **SHALL** be omitted from the resource.  

##### Missing Must Support and Mandatory Data

If the data element is a mandatory element (minimum cardinality is > 0), the element **SHALL** be present *even if* the source system (producer) does not know the value or the reason the value is absent. In this circumstance the requirements defined by AU Core for [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data) **SHALL** be applied:

#### Empty Sections

<div class="stu-note" markdown="1">
The proposal on empty sections is available: <a href="https://build.fhir.org/ig/hl7au/au-fhir-ps/branches/ft_conf-proposal/general-requirements.html">Narrative conformance requirements</a> e.g. Missing Data, Empty Sections</li>.

This proposal will be voted on in next AU PS FHIR IG Call this Friday: <a href="https://confluence.hl7.org/spaces/HAFWG/pages/358878850/2025-07-11+AU+Patient+Summary+FHIR+IG+Agenda+Minutes">2025-07-11 AU Patient Summary FHIR IG Agenda/Minutes</a>.
</div><!-- stu-note -->

### Suppressed Data

<div class="stu-note" markdown="1">
The proposal on suppressed data is available: <a href="https://build.fhir.org/ig/hl7au/au-fhir-ps/branches/ft_conf-proposal/general-requirements.html">Narrative conformance requirements</a> e.g. Missing Data, Empty Sections</li>.

This proposal will be voted on in next AU PS FHIR IG Call this Friday: <a href="https://confluence.hl7.org/spaces/HAFWG/pages/358878850/2025-07-11+AU+Patient+Summary+FHIR+IG+Agenda+Minutes">2025-07-11 AU Patient Summary FHIR IG Agenda/Minutes</a>.
</div><!-- stu-note -->

### Must Support and Obligation
Labelling an element *[Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport)* means that systems that produce or consume resources **SHALL** provide support for the element in some meaningful way. The FHIR standard does not define exactly what 'meaningful' support for an element means, but indicates that a profile **SHALL** make clear exactly what kind of support is required when an element is labelled as *Must Support*.

In AU PS, the meaning of *Must Support* is specified in terms of [Obligation Codes](https://hl7.org/fhir/extensions/CodeSystem-obligation.html) in [obligation extensions](https://hl7.org/fhir/extensions/StructureDefinition-obligation.html) on the element definition. The obligation codes used to define the minimum obligations of *Must Support* elements in this implementation guide are reiterated below.

Actor | Code | Definition | Notes
--- | --- | --- | ---
[AU PS Consumer actor](ActorDefinition-au-ps-actor-consumer.html) | [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) | Conformant applications SHALL handle the meaning of this element correctly. |  This rule is vague in that doesn't specify any particular handling of the element. But it's important because an application that ignores this element is non-conformant. A good example would be a status code of 'entered-in-error' - how exactly a Resource Consumer handles this depends on the use case etc., but the application can never simply ignore such a status code. Note that whether the resource or information from it is stored for later use is irrelevant - when the resource or information in it is processed, the consequences of the element are considered.
| [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) | Conformant applications SHOULD display the value of this element when presenting the data from the resource to a human user. | Exactly how it is displayed is not specified, but it means that a human looking at the content of the resource is made aware of the value of the element so that they can consider the meaning of the resource.
[AU PS Producer actor](ActorDefinition-au-ps-actor-producer.html) |[SHALL:populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58populate)|Conformant applications producing resources SHALL include this element if a value is known and allowed to be shared| This implementation obligation means that whenever the producer knows the correct value for an element, it populates it. This is NOT the same as cardinality, as a 'populate' element can be omitted if no data exists or the data that exists is prohibited from being shared.
| [SHALL:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58able-to-populate) | Conformant applications producing resources SHALL be able to correctly populate this element. | Typically, this means that an application needs to demonstrate during some conformance testing process that there are some conditions under which it populates the element with a correct value. (i.e. not a data-absent-reason or equivalent.) This obligation does not impose expectations on the circumstances in which the element will be sent, only that it can be in at least some situations.
| [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58populate-if-known) | Conformant applications producing resources SHALL correctly populate this element if they know a value for the element, but it is acceptable if the system is unable to ever know a value for the element. | This obligation does not impose a requirement to be able to know a value, unlike populate and able-to-populate which do. 'Knowing' an element means that a value for the element is available in memory, persistent store, or is otherwise available within the system claiming conformance.
| [SHOULD:populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate)|Conformant applications producing resources SHOULD include this element if a value is known and allowed to be shared.| This implementation obligation means that whenever the producer knows the correct value for an element, it should populate it.
| [SHOULD:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known) | Conformant applications producing resources SHOULD correctly populate this element if they know a value for the element, but it is acceptable if the system is unable to ever know a value for the element. | This obligation does not impose a requirement to be able to know a value, unlike populate and able-to-populate which do. 'Knowing' an element means that a value for the element is available in memory, persistent store, or is otherwise available within the system claiming conformance. 
|  [MAY:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-MAY.58able-to-populate)| Conformant applications producing resources MAY be able to correctly populate this element. | Typically, this means that an application needs to demonstrate during some conformance testing process that there are some conditions under which it populates the element with a correct value. (i.e. not a data-absent-reason or equivalent.) 
{:.grid}

*Must Support* elements are treated differently between [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html) and [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) actors. *Must Support* on a profile element **SHALL** be interpreted as follows.

#### Presentation of Must Support and obligation in profiles
All elements with *Must Support* in AU PS are accompanied by an explicit obligation that identifies the expectations for one or more actors. When rendered in an implementation guide, each profile is presented in different formal views under tabs labelled "Differential Table", "Key Elements Table", and "Snapshot Table". Elements flagged with *Must Support* and stated obligations in these views are represented by <span style="padding-left: 3px; padding-right: 3px; color: white; background-color: red" title="This element must be supported">S</span><span style="padding-left: 3px; padding-right: 3px; color: white; background-color: red" title="This element has obligations">O</span> as shown below. 

 <div> 
    <img src="allergyintolerance-keyelementstable.png" alt="AU PS AllergyIntolerance Key Elements Table" style="width:75%"/>
  </div>
*Figure 1: Key Elements Table View*
<br/>

Implementers need to refer to the "Key Elements Table" to see the full set of elements that are mandatory or *Must Support* with obligations, and the full set of terminology requirements.  Implementers need to be aware that the full set of constraints (i.e. invariants) are only presented in the "Detailed Descriptions" tab or the raw representation (e.g. XML or JSON) of the profile.


#### Interpreting profile elements labelled Must Support

Profiles defined in this implementation publication flag *Must Support* on elements (e.g. `Patient.name`) and sub-elements of a data type (e.g. `Patient.name.use`). 
The explanation on how to interpret *Must Support* for an element does not address rules defined in each profile - which may limit or extend what is allowed for each element.

The sub-elements for each supported element in a profile are defined by a combination of the data type from the core specification and any additional rules included in the profile. A profile may include rules that:
- limit what is considered 'valid'
- extend the potential sub-elements by including an extension

For example, the profile [AU PS Patient](StructureDefinition-au-ps-patient.html) limits what is considered valid for the element `Patient.name` with the invariant "**au-core-pat-02:** At least one patient name shall have a family name".

Typically AU PS profiles will inherit extended sub-elements from the base HL7 AU Core profile (which itself is based on an HL7 AU Base profile), e.g. the element `Medication.code` in profile [AU PS Medication](StructureDefinition-au-ps-medication.html) is of type CodeableConcept and is extended by inheriting a medicine specific sub-element `Medication.code.coding.extension` [Medication Type extension](http://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-medication-type.html) from the source profile [AU Base Medication](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medication.html). 

The full set of sub-elements is visible in the "Key Elements Table" or "Snapshot Table" which shows the sub-elements defined in this profile (shown in the "Differential Table") and the sub-elements inherited from a base profile.


###### Must Support - Primitive Elements
Primitive elements are single elements with a primitive value. If a primitive element is labelled as *Must Support*: 
- AU PS Producers **SHALL** correctly populate the element if a value is known. 
- AU PS Consumers **SHALL** consume resources if the element is present and containing any valid value, and **SHOULD** display the value of this element when presenting the data from the resource to a human user.

For example, the AU PS Organization Profile `name` element is a primitive string datatype. Therefore, when claiming conformance to this profile:
- AU PS Producers **SHALL** correctly populate a value in `Organization.name` if a value is known.
- AU PS Consumers **SHALL** consume the Organization resource if `Organization.name` is present and containing any valid value , and **SHOULD** display the value of `Organization.name` when presenting the data from the resource to a human user.

##### Must Support - Complex Elements
Complex elements are composed of primitive and/or other complex elements. Elements may have additional rules defined in the profile that also apply, e.g. terminology binding, or invariants. 

If a complex element is labelled as *Must Support*:
- AU PS Producers **SHALL** correctly populate the element with at least one of the sub-element values if the value is known.
- AU PS Consumers **SHALL** consume resources if the element is present and containing any valid sub-element, and **SHOULD** display the value of this element when presenting the data from the resource to a human user.

For example, the AU PS MedicationRequest Profile `note` element is labelled *Must Support* and has no *Must Support* sub-elements. When claiming conformance to this profile:
- AU PS Producers **SHALL** correctly populate a value in any valid `MedicationRequest.note` sub-element if a value is known e.g. `MedicationRequest.note.text`.
- AU PS Consumers **SHALL** consume the MedicationRequest resource if `MedicationRequest.note` is present and containing any valid sub-elements, and **SHOULD** display the value of `MedicationRequest.note` when presenting the data from the resource to a human user.

If a sub-element is labelled as *Must Support*: 
- AU PS Producers **SHALL** correctly populate the element with all *Must Support* sub-elements for which a value is known. 
- AU PS Consumers **SHALL** consume resources if *Must Support* sub-elements are present and containing any valid value, and **SHOULD** display the value of this element when presenting the data from the resource to a human user.

For example, in the AU PS Practitioner Profile, the `name` element is labelled *Must Support* and has *Must Support* sub-elements `family` and `given`. When claiming conformance to this profile:
- AU PS Producers **SHALL** correctly populate a value in `Practitioner.name.family` and `Practitioner.name.given` if the value for those sub-elements is known.
- AU PS Consumers **SHALL** consume a Patient resource if `Practitioner.name` is present and contains valid values in `Practitioner.name.family` and `Practitioner.name.given` sub-elements, and **SHOULD** display the value of at least the sub elements`Practitioner.name.family` and `Practitioner.name.given` when presenting the data from the resource to a human user.

###### Must Support - Resource References
Some elements labelled as *Must Support* reference multiple resource types or profiles such as `Observation.performer`. In such cases: 
- AU PS Producers **SHALL** correctly populate the element with at least one referenced resource or allowed profile if the value is known. 
- AU PS Consumers **SHALL** consume resources if the element is present and containing any valid referenced resource or profiles, and **SHOULD** display the value of this element when presenting the data from the resource to a human user.

The table below provides a list of AU PS profile elements that allow multiple referenced resource types or profiles.

Profile |Must Support Element|Reference
---|---|---
AU PS Composition|Composition.author|AU PS Practitioner, AU PS PractitionerRole, Device, AU PS Patient, AU PS RelatedPerson, AU PS Organization
AU PS Composition|Composition.author|AU PS Patient, AU PS RelatedPerson, AU PS Practitioner, AU PS PractitionerRole, AU PS Organization
AU PS Composition|Composition.section.entry:medicationStatementOrRequest|AU PS MedicationStatement, AU PS MedicationRequest
DiagnosticReport (IPS)|DiagnosticReport.subject|Patient (IPS), Group
DiagnosticReport (IPS)|DiagnosticReport.performer|Practitioner (IPS), PractitionerRole (IPS), Organization (IPS), CareTeam
AU PS Encounter|Encounter.participant.individual|AU PS Practitioner, AU PS PractitionerRole, AU PS RelatedPerson
DiagnosticReport (IPS)|DiagnosticReport.result:observation-results|Observation Results - Laboratory/Pathology (IPS), Observation Results - Radiology (IPS)
AU PS Encounter|Encounter.reasonReference|AU PS Condition, Observation, AU PS Procedure
AU PS Pathology Result Observation|Observation.performer|AU PS Practitioner, AU PS PractitionerRole, AU PS Organization, AU PS Patient, AU PS RelatedPerson
AU PS Procedure|Procedure.reasonReference|AU PS Condition, Observation, AU PS Procedure, DocumentReference
AU PS MedicationRequest|MedicationRequest.requester|AU PS Practitioner, AU PS PractitionerRole, AU PS Organization, AU PS Patient, AU PS RelatedPerson
AU PS MedicationRequest|MedicationRequest.reasonReference|AU PS Condition, Observation
AU PS MedicationStatement|MedicationStatement.reasonReference|AU PS Condition, Observation, AU Base Diagnostic Report
{:.grid}


###### Must Support - Choice of Data Types
Some elements labelled as *Must Support* allow different data types such as `Observation.effective[x]`. In such cases:
- AU PS Producers **SHALL** correctly populate the element with at least one data type allowed by the element definition if the value is known.
- AU PS Consumers **SHALL** consume resources if the element is present and containing any valid data type allowed by the element definition, and **SHOULD** display the value of this element when presenting the data from the resource to a human user.

The table below provides a list of AU PS profile elements that allow multiple data types.

Profile |Must Support Element|Data Types
---|---|---
AU PS AllergyIntolerance|AllergyIntolerance.onset[x]|dateTime, age, Period, Range
AU PS Condition|Condition.onset[x]|dateTime, age, Period, Range
AU PS Condition|Condition.abatement[x]|dateTime, age, Period, Range
AU PS Immunization|Immunization.occurrence[x]|dateTime, string
AU PS MedicationRequest|MedicationRequest.medication[x]|CodeableConcept, Reference
AU PS MedicationStatement|MedicationStatement.medication[x]|CodeableConcept, Reference
Observation Results - Radiology (IPS)|Observation.effective[x]|dateTime, Period, Timing, instant
Observation Results - Radiology (IPS)|Observation.value[x]|Quantity, CodeableConcept, string, boolean, integer, Range, Ratio, SampledData, time, dateTime, Period
AU PS Pathology Result Observation|Observation.effective[x]|dateTime, Period,
AU PS Pathology Result Observation|Observation.value[x]|Quantity, CodeableConcept, string, boolean, integer, Range, Ratio, SampledData, time, dateTime, Period
AU PS Pathology Result Observation|Observation.component.value[x]|Quantity, CodeableConcept, string, boolean, integer, Range, Ratio, SampledData, time, dateTime, Period
AU PS Procedure|Procedure.performed[x]|dateTime, Period, string, Age, Range
{:.grid}

###### Must Support - Choice of Identifiers
A profile may support one or more than one identifier type and will include the supported identifiers in a profile by slicing the element and placing *Must Support* on each identifier slice. In such cases:
- AU PS Producers **SHALL** correctly populate the element with identifiers from any supported identifier type where the identifier is known.
- AU PS Consumers **SHALL** consume resources if the element is present and containing any identifier type allowed by the element definition, and **SHOULD** display the value of each populated identifier when presenting the data from the resource to a human user.

The table below provides a list of AU PS profile elements that allow multiple identifier types.

Profile |Must Support Element|Supported Identifiers
---|---|---
AU PS Organization|Organization.identifier|HPI-O, Australian Business Number
AU PS Patient|Patient.identifier|IHI, Medicare Card Number, DVA Number
AU PS Practitioner|Practitioner.identifier|HPI-I
AU PS PractitionerRole|PractitionerRole.identifier|Medicare Provider Number
{:.grid}

For example, the profile [AU PS Patient](StructureDefinition-au-ps-patient.html) requires support for the following choices `Patient.identifier` defined in [AU Base Patient](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-patient.html) to support Individual Healthcare Identifier (IHI), Medicare Card Number, Department of Veterans' Affairs (DVA) Number. When claiming conformance to the AU PS Patient Profile:
- AU PS Producers **SHALL** correctly populate `Patient.identifier` with an IHI, or Medicare Care Number, or DVA Number, or any combination of them.
- AU PS Consumers **SHALL** consume Patient resource if `Patient.identifier` is present containing any valid value. A valid value may be an IHI, Medicare Care Number, or DVA Number identifier, or may be some other allowed identifier. The AU PS Consumer **SHOULD** display the value of each populated identifier type (IHI, Medicare Number, DVA Number, or some other identifier) when presenting the data from the resource to a human user.

Systems **MAY** support populating other identifiers, but this is not a requirement of AU PS.

###### Must Support - Choice of Profile Elements

A resource may support two elements that are used to indicate a reason, e.g. `Encounter.reasonCode` and `Encounter.reasonReference` in the profile [AU PS Encounter](StructureDefinition-au-ps-encounter.html). In such cases:
- AU PS Producers **SHALL** correctly populate at least one element choice if the value is known.
- AU PS Consumers **SHALL** consume resources if any element allowed by the profile is present and containing any valid value. 

The table below lists the applicable profiles and elements in AU PS.

Profile |Must Support Choice Elements
---|---
AU PS Encounter|Encounter.reasonCode, Encounter.reasonReference
AU PS Procedure|Procedure.reasonCode, Procedure.reasonReference
AU PS MedicationRequest|MedicationRequest.reasonCode, MedicationRequest.reasonReference
AU PS MedicationStatement|MedicationStatement.reasonCode, MedicationStatement.reasonReference
{:.grid}


###### Must Support - Choice of Terminology (This needs to be worked on to account for IPS data type profiles)

In AU PS, elements that define support for more than one value set only apply to the [Coding](http://hl7.org/fhir/R4/datatypes.html#Coding) part of the element and are not intended to prevent systems from supplying only a text value. In such cases:
- AU PS Producers **SHALL** correctly populate the element with concepts from each supported value set where the applicable concept is known.
- AU PS Consumers **SHALL** consume the resource if the element is present and containing any valid value, and **SHOULD** display the value of this element when presenting the data from the resource to a human user.

The table below lists the applicable profiles and elements in AU PS that support multiple value sets.

Profile |Must Support Sub-Element|Terminology Choices
---|---
AU PS Immunization|Immunization.code.coding|[Australian Medicines Terminology Vaccine](https://healthterminologies.gov.au/fhir/ValueSet/amt-vaccine-1), [Australian Immunisation Register Vaccine](https://healthterminologies.gov.au/fhir/ValueSet/australian-immunisation-register-vaccine-1)
AU PS Medication|Medication.code.coding|[Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1), [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html)
AU PS MedicationRequest|MedicationRequest.code.coding|[Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1), [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html)
AU PS MedicationStatement|MedicationStatement.code.coding|[Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1), [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html)
{:.grid}

For example, the profile [AU PS Medication](StructureDefinition-au-ps-medication.html) requires support for the following terminology choices `Medication.code.coding` defined in [AU Base Medication](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medication.html) to support [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) and [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html) as indicated by flagging *Must Support* on those two terminology slices.

When claiming conformance to the AU PS Medication profile: 
- AU PS Producers **SHALL** correctly populate `Medication.code.coding` with either a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, if a coded value is known. AU PS Producers **MAY** populate with only text if no coded value is known.
- AU PS Consumers **SHALL** consume a Medication resource if `Medication.code.coding` is present and containing any valid value. A valid value may be text, or may be a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, or some other code. AU PS Consumers **SHOULD** display the value of this element when presenting the data from the resource to a human user.

Systems **MAY** populate other code systems but this is not a requirement of AU PS.