{::options toc_levels="1..4"/}

### Conforming to AU Patient Summary (AU PS)

Systems claiming conformance to AU PS will represent digital health information using the content models of [AU PS profiles](profiles-and-extensions.html) AND implement the requirements of one or both [AU PS actors](actors.html).

The requirements of the FHIR standard and [FHIR Conformance Rules](http://hl7.org/fhir/conformance-rules.html) apply, and define the use of terms in this guide including the conformance verbs - **SHALL**, **SHALL NOT**, **SHOULD**, **SHOULD NOT**, **MAY**.

Implementers are advised to be familiar with the requirements of the FHIR standard and IPS when implementing AU PS, in particular:
- [IPS Generation and Data Inclusion](https://build.fhir.org/ig/HL7/fhir-ips/Generation-and-Data-Inclusion.html#generation-and-data-inclusion)
- [IPS Narrative and Language Translation](https://build.fhir.org/ig/HL7/fhir-ips/Design-Conventions.html#narrative-and-language-translation)
- [FHIR Terminology requirements](http://hl7.org/fhir/R4/terminologies.html)
- [FHIR Documents](https://hl7.org/fhir/R4/documents.html) and [FHIR Clinical Documents](https://hl7.org/fhir/uv/fhir-clinical-document/)
- [FHIR RESTful API](http://hl7.org/fhir/R4/http.html) 
- [FHIR Search](http://hl7.org/fhir/R4/search.html)
- [FHIR Resource formats](http://hl7.org/fhir/R4/resource.html)
- [FHIR Data Types](http://hl7.org/fhir/R4/datatypes.html)

### Conformance Artifacts

#### AU PS Profiles and Extensions
The [Profiles and Extensions](profiles-and-extensions.html) page lists the AU PS profiles and extensions defined for this implementation guide. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the minimum elements, extensions, vocabularies and value sets that **SHALL** be present and constrains the way elements are used when conforming to the profile.

AU PS profile elements include mandatory and *Must Support* requirements. [Mandatory elements](#mandatory-elements) are required and have a minimum cardinality > 0. [Must Support](#must-support-and-obligation) elements have defined conformance obligations in AU PS.

#### AU PS Actors
The [Actor Definitions](actors.html) page lists the AU PS actors defined for this implementation guide and the requirements for implementing that actor. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the obligations for an AU PS actor when implementing that profile.

### Mandatory Elements
Mandatory elements are elements with minimum cardinality > 0. When an element is mandatory, the data is expected to always be present. Very rarely, it may not be, and in this circumstance the requirements defined by AU Core for [Missing Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-data) **SHALL** be applied. 

An element can be both *Must Support* and mandatory, and in this circumstance the requirements defined for [Missing Must Support and Mandatory Data](general-requirements.html#missing-must-support-and-mandatory-data) **SHALL** be applied.

The convention in this guide is to mark all mandatory and conditionally mandatory elements as *Must Support* unless they are nested under an optional element.

### Missing Data, Empty Sections, Known Absence of Data
It is important to differentiate between the following mutually exclusive circumstances:
* Affirmatively stating that a patient has "no known X" or "no history of X" (for example, that a patient has no known allergies). 
* Not having data in the record for a particular section (for example, where a source system does not have information on a patient's allergies). 
* Asserting that this data is not available due to a workflow reason (for example, allergies were not reviewed and are unknown). 
* Not having data for a particular element (for example, the onset date of a particular allergy is not available in the system and the system does not know the reason for the absence).

In the above circumstances the following is applied:
* When stating "no known X" or "no history of X", systems **SHOULD** implement the guidance of the [No Known X](general-requirements.html#no-known-x) section.
* Where data is missing for a section and the reason is not known, systems **SHALL** implement the requirements of the [Empty Sections](general-requirements.html#empty-sections) section.
* Where data is not available due to a known workflow reason, systems **SHOULD** implement the requirements of the [Known Absence of Data Due to Workflow](general-requirements.html#known-absence-of-data-due-to-workflow) section.
* Where data is missing for an element within a resource and the reason is not known, systems **SHALL** implement the requirements of the [Missing Data](general-requirements.html#missing-data) section.

#### Missing Data

##### Missing Must Support and Optional Data

If the source system (AU PS Producer) does not know the value for an optional element (minimum cardinality = 0), including elements labelled *Must Support*, as per the requirements defined in [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-optional-data), the data element **SHALL** be omitted from the resource.  

##### Missing Must Support and Mandatory Data

If the data element is a mandatory element (minimum cardinality is > 0), the element **SHALL** be present *even if* the source system (AU PS Producer) does not know the value or the reason the value is absent. In this circumstance, the requirements defined by AU Core for [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data) **SHALL** be applied.

Example: MedicationRequest resource where status and requester are missing
~~~
  ...
  {
    "resourceType" : "MedicationRequest",
    "status" : "unknown",
    "intent" : "order",
    "medicationCodeableConcept" : {
      "coding" : [
        {
          "system" : "http://snomed.info/sct",
          "code" : "79115011000036100",
          "display" : "Paracetamol 500 mg + codeine phosphate hemihydrate 30 mg tablet"
        }
      ]
    },
    ...
    "authoredOn" : "2018-07-15",
    "requester" : {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/data-absent-reason",
          "valueCode" : "unknown"
        }
      ]
    },
  ...
~~~
#### Empty Sections

An AU PS Producer **SHOULD** omit non-mandatory sections when the source system does not have any information and does not know the reason the information is absent.

For a mandatory section (minimum cardinality is > 0), the section **SHALL** be present *even if* the source system (AU PS Producer) does not have any information for that section or know the reason the information is absent. In this circumstance, an AU PS Producer **SHALL**:

* use the code `unavailable` from the [List Empty Reasons](http://terminology.hl7.org/CodeSystem/list-empty-reason) code system

AU PS Consumers are advised that other meaningful values can be captured in `Composition.section.emptyReason` beyond missing or suppressed.
  
  Example: AU PS - Allergies and Intolerances Section where the patient's allergy information is not available.
  ~~~
    ...
    "section" : [
       {
        "title" : "Allergies and Intolerances",
        "code" : {
        "coding" : [
          {
            "system" : "http://loinc.org",
            "code" : "48765-2",
            "display" : "Allergies and adverse reactions Document"
          }
        ]
        },
        "text" : {
        "status" : "generated",
        "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\" xml:lang=\"en-AU\" lang=\"en-AU\">There is no information available regarding the consumer's allergy conditions.</div>"
        },
        "emptyReason" : {
          "coding" : [
            {
            "system" : "http://terminology.hl7.org/CodeSystem/list-empty-reason",
            "code" : "unavailable",
            "display" : "Unavailable"
            }
          ],
          "text" : "No information available"
        }
      },
    ...
  ~~~

#### Known Absence of Data Due to Workflow

Where the system does not have information for a particular section and there is a known workflow reason (for example, the patient preferred not to answer), the system **SHOULD** represent that reason by populating `Composition.section.emptyReason`:
* Prefer not to answer may be represented by sending the [Data Absent Reason](http://terminology.hl7.org/CodeSystem/data-absent-reason) code "asked-declined"
* Asked but not known may be represented by sending the [Data Absent Reason](http://terminology.hl7.org/CodeSystem/data-absent-reason) code "asked-unknown"
* Where the workflow does not obtain the information, it may be represented by sending the [List Empty Reason](https://hl7.org/fhir/R4/codesystem-list-empty-reason.html) code "notasked"

Example: AU PS - Allergies and Intolerances Section where there is a workflow reason the patient's allergy information is not available.
~~~
  ...
  "section" : [
    {
      "title" : "Allergies and Intolerances",
      "code" : {
      "coding" : [
        {
          "system" : "http://loinc.org",
          "code" : "48765-2",
          "display" : "Allergies and adverse reactions Document"
        }
      ]
      },
      "text" : {
      "status" : "generated",
      "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\" xml:lang=\"en-AU\" lang=\"en-AU\">The patient was not asked about allergies.</div>"
      },
      "emptyReason" : {
        "coding" : [
          {
           "system" : "http://terminology.hl7.org/CodeSystem/list-empty-reason",
            "code" : "notasked",
            "display" : "Not Asked"
          }
        ],
        "text" : "Patient was not asked"
      }
    },
  ...
~~~

#### No Known X

Where the system can assert "no known X" (for example, no known conditions) or "no history of X" (for example, no history of cardiovascular system disease), the system **SHOULD** populate `Composition.section.entry` in accordance with the relevant profile specific implementation guidance. 

For example, to represent that a patient does not have an allergy or category of allergies, an appropriate negation code (e.g. 716186003 \|No known allergy\| or 1003774007 \|No known Hevea brasiliensis latex allergy\|) is used in `AllergyIntolerance.code` as per the profile specific implementation guidance.

In AU PS this approach is preferred to using `Composition.section.emptyReason` due to the widely known and implemented patterns established within FHIR, IPS, and AU Core to assert "no known X" or "no history of X". 


Example: Condition resource representing 'No Known Problems'
~~~
  ...
  {
    "resourceType" : "Condition",
    "clinicalStatus" : "active",
    "code" : {
      "coding" : [
        {
          "system" : "http://snomed.info/sct",
          "code" : "160245001",
          "display" : "No current problems or disability"
        }
      ]
    },
  ...
~~~

### Suppressed Data

In some circumstances, specific pieces of data are hidden:
* if an optional section (minimum cardinality = 0) is not able to be shared, it **MAY** be omitted; but if provided use the code `unavailable` or `withheld` from the [List Empty Reason](https://hl7.org/fhir/R4/codesystem-list-empty-reason.html) in `Composition.section.emptyReason`.
* if a mandatory section (minimum cardinality > 0) is not able to be shared, use the code `unavailable` or `withheld` from the [List Empty Reason](https://hl7.org/fhir/R4/codesystem-list-empty-reason.html) in `Composition.section.emptyReason`.
* if an optional element (minimum cardinality = 0) is not able to be shared, it **SHALL** be omitted.
* if a mandatory element (minimum cardinality > 0) is not able to be shared, use the code `unknown` or `masked` from the [DataAbsentReason Code System](http://terminology.hl7.org/CodeSystem/data-absent-reason) following the section on [Missing Data](#missing-data).

    Example: AU PS - Allergies and Intolerances Section where the patient's allergy information is not allowed to be shared.
    ~~~
        ...
        "section" : [
            {
              "title" : "Allergies and Intolerances",
              "code" : {
                "coding" : [
                    {
                    "system" : "http://loinc.org",
                    "code" : "48765-2",
                    "display" : "Allergies and adverse reactions Document"
                  }
                ]
              },
              "text" : {
                "status" : "generated",
                "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\" xml:lang=\"en-AU\" lang=\"en-AU\">This information is withheld.</div>"
              },
              "emptyReason" : {
                "coding" : [
                    {
                    "system" : "http://terminology.hl7.org/CodeSystem/list-empty-reason",
                    "code" : "withheld",
                    "display" : "Withheld"
                    }
                ],
                "text" : "Withheld"
              }
            },
        ...
    ~~~
    

### Must Support and Obligation
Labelling an element *[Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport)* means that systems that produce or consume resources **SHALL** provide support for the element in some meaningful way. The FHIR standard does not define exactly what 'meaningful' support for an element means, but indicates that a profile **SHALL** make clear exactly what kind of support is required when an element is labelled as *Must Support*.

In AU PS, the meaning of *Must Support* is specified in terms of [Obligation Codes](https://hl7.org/fhir/extensions/CodeSystem-obligation.html) in [obligation extensions](https://hl7.org/fhir/extensions/StructureDefinition-obligation.html) on the element definition. The obligation codes used to define the minimum obligations of *Must Support* elements in this implementation guide are reiterated below.

Actor | Code | Definition | Notes
--- | --- | --- | ---
[AU PS Consumer actor](ActorDefinition-au-ps-actor-consumer.html) | [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) | Conformant applications SHALL handle the meaning of this element correctly. |  This rule is vague in that doesn't specify any particular handling of the element. But it's important because an application that ignores this element is non-conformant. A good example would be a status code of 'entered-in-error' - how exactly a Resource Consumer handles this depends on the use case etc., but the application can never simply ignore such a status code. Note that whether the resource or information from it is stored for later use is irrelevant - when the resource or information in it is processed, the consequences of the element are considered. In AU PS, all elements marked as _Must Support_ have this obligation applied.
| [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) | Conformant applications SHOULD display the value of this element when presenting the data to a human user. | Exactly how it is displayed is not specified, but it means that a human looking at the content of the resource is made aware of the value of the element so that they can consider the meaning of the resource. In AU PS, most elements marked as _Must Support_ have this obligation applied.
[AU PS Producer actor](ActorDefinition-au-ps-actor-producer.html) |[SHALL:populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58populate)|Conformant applications producing resources SHALL include this element if a value is known and allowed to be shared| This implementation obligation means that whenever the producer knows the correct value for an element, it populates it. This is NOT the same as cardinality, as a 'populate' element can be omitted if no data exists or the data that exists is prohibited from being shared. SHALL:populate combines able-to-populate and populate-if-known for the element. 
| [SHALL:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58able-to-populate) | Conformant applications producing resources SHALL be able to correctly populate this element. | Typically, this means that an application needs to demonstrate during some conformance testing process that there are some conditions under which it populates the element with a correct value. (i.e. not a data-absent-reason or equivalent.) This obligation does not impose expectations on the circumstances in which the element will be sent, only that it can be in at least some situations.
| [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58populate-if-known) | Conformant applications producing resources SHALL correctly populate this element if they know a value for the element, but it is acceptable if the system is unable to ever know a value for the element. | This obligation does not impose a requirement to be able to know a value, unlike populate and able-to-populate which do. 'Knowing' an element means that a value for the element is available in memory, persistent store, or is otherwise available within the system claiming conformance. With the exception of AU PS Composition, all profiles referenced by AU PS Bundle have this obligation applied to elements marked as _Must Support_.
| [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate) | Conformant applications producing resources SHOULD be able to correctly populate this element. | Typically, this means that an application needs to demonstrate during some conformance testing process that there are some conditions under which it populates the element with a correct value. (i.e. not a data-absent-reason or equivalent.) This obligation does not impose expectations on the circumstances in which the element will be sent, only that it can be in at least some situations.
| [SHOULD:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known) | Conformant applications producing resources SHOULD correctly populate this element if they know a value for the element, but it is acceptable if the system is unable to ever know a value for the element. | This obligation does not impose a requirement to be able to know a value, unlike populate and able-to-populate which do. 'Knowing' an element means that a value for the element is available in memory, persistent store, or is otherwise available within the system claiming conformance. 
|  [MAY:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-MAY.58able-to-populate)| Conformant applications producing resources MAY be able to correctly populate this element. | Typically, this means that an application needs to demonstrate during some conformance testing process that there are some conditions under which it populates the element with a correct value. (i.e. not a data-absent-reason or equivalent.)  
{:.grid}

*Must Support* elements are treated differently between [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html) and [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) actors. *Must Support* on a profile element **SHALL** be interpreted as follows.

#### Presentation of Must Support and Obligation in Profiles
All elements with *Must Support* in AU PS are accompanied by an explicit obligation that identifies the expectations for one or more actors. When rendered in an implementation guide, each profile is presented in different formal views under tabs labelled "Differential Table", "Key Elements Table", and "Snapshot Table". Elements labelled with *Must Support* and stated obligations in these views are represented by <span style="padding-left: 1px; padding-right: 1px; color: white; background-color: red" title="This element must be supported">S</span><span style="padding-left: 1px; padding-right: 1px; color: white; background-color: red" title="This element has obligations">O</span> as shown below. 

 <div> 
    <img src="allergyintolerance-keyelementstable.png" alt="AU PS AllergyIntolerance Key Elements Table" style="width:75%"/>
  </div>
*Figure 1: Key Elements Table View*
<br/>

Implementers need to refer to the "Key Elements Table" to see the full set of elements that are mandatory or *Must Support* with obligations, and the full set of terminology requirements.  Implementers need to be aware that the full set of constraints (i.e. invariants) are only presented in the "Detailed Descriptions" tab or the raw representation (e.g. XML or JSON) of the profile.


#### Interpreting Profile Elements Labelled Must Support

The section is provided as additional support in understanding the application of *Must Support* and Obligations on elements in AU PS. This section does not override the Obligations defined for an actor - implementers are recommended to also read the profile specific implementation guidance for any qualifying requirements placed on the Obligations for a *Must Support* element.

Profiles defined in this implementation guide flag *Must Support* on elements (e.g. `Patient.name`) and sub-elements of a data type (e.g. `Patient.name.use`). The explanation on how to interpret *Must Support* for an element does not address rules defined in each profile - which may limit or extend what is allowed for each element.

The sub-elements for each supported element in a profile are defined by a combination of the data type from the core specification and any additional rules included in the profile. A profile may include rules that:
- limit what is considered 'valid'
- extend the potential sub-elements by including an extension

For example, the profile [AU PS Patient](StructureDefinition-au-ps-patient.html) limits what is considered valid for the element `Patient.name` with the invariant "**au-core-pat-02:** At least one patient name shall have a family name".

Typically AU PS profiles will inherit extended sub-elements from the base HL7 AU Core profile (which itself is based on an HL7 AU Base profile), e.g. the element `Medication.code` in profile [AU PS Medication](StructureDefinition-au-ps-medication.html) is of type CodeableConcept and is extended by inheriting a medicine specific sub-element `Medication.code.coding.extension` [Medication Type extension](http://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-medication-type.html) from the source profile [AU Base Medication](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medication.html). 

The full set of sub-elements is visible in the "Key Elements Table" or "Snapshot Table" which shows the sub-elements defined in this profile (shown in the "Differential Table") and the sub-elements inherited from a base profile.

##### Must Support - Composition Sections
Obligations vary significantly for elements in the AU PS Composition profile, in particular obligations on `Composition.section` reflect the expectations of [The "IPS"](https://hl7.org/fhir/uv/ips/STU2/Structure-of-the-International-Patient-Summary.html) and  [ISO 27269](https://www.iso.org/standard/79491.html). A summary is provided below:
- AU PS Consumers **SHALL** handle the Composition section if present and containing any valid value, and **SHOULD** display the content of the section when presenting the data to a human user.
- For all mandatory sections (`Composition.section` minimum cardinality > 0) AU PS Producers **SHALL** correctly populate the section if a value is known, **SHALL** be capable of populating `Composition.section.entry` with the referenced profiles, and **SHOULD** correctly populate `Composition.section.entry` if a value is known. 
- For all recommended sections AU PS Producers **SHOULD** correctly populate the section if a value is known and **SHOULD** correctly populate `Composition.section.entry` if a value is known. 
- For all optional or undefined sections AU PS Producers **MAY** correctly populate the section if a value is known and **MAY** correctly populate `Composition.section.entry` if a value is known. 

See [Structure of the Australian Patient Summary (AU PS)](the-aups.html#structure-of-the-au-ps) for information on the mandatory, recommended, and optional sections.

##### Must Support - Primitive Elements
Primitive elements are single elements with a primitive value. If a primitive element is labelled as *Must Support*: 
- AU PS Producers **SHALL** correctly populate the element if a value is known. 
- AU PS Consumers **SHALL** handle the element if present and containing any valid value, and **SHOULD** display the value of this element (if the SHOULD:display Obligation is defined) when presenting the data to a human user.

For example, the AU PS Organization Profile `name` element is a primitive string datatype. Therefore, when claiming conformance to this profile:
- AU PS Producers **SHALL** correctly populate a value in `Organization.name` if a value is known.
- AU PS Consumers **SHALL** handle the `Organization.name` if present and containing any valid value, and **SHOULD** display the value of `Organization.name` when presenting the data to a human user.

##### Must Support - Complex Elements
Complex elements are composed of primitive and/or other complex elements. Elements may have additional rules defined in the profile that also apply, e.g. terminology binding, or invariants. 

If a complex element is labelled as *Must Support*:
- AU PS Producers **SHALL** correctly populate the element with at least one of the sub-element values if the value is known.
- AU PS Consumers **SHALL** handle the element if present and containing any valid sub-element, and **SHOULD** display the value of this element (if the SHOULD:display Obligation is defined) when presenting the data to a human user.

For example, the AU PS AllergyIntolerance Profile `note` element is labelled *Must Support* and has no *Must Support* sub-elements. When claiming conformance to this profile:
- AU PS Producers **SHALL** correctly populate a value in any valid `AllergyIntolerance.note` sub-element if a value is known e.g. `AllergyIntolerance.note.text`.
- AU PS Consumers **SHALL** handle `AllergyIntolerance.note` if present and containing any valid sub-elements, and **SHOULD** display the value of `AllergyIntolerance.note` when presenting the data to a human user.

If a sub-element is labelled as *Must Support*: 
- AU PS Producers **SHALL** correctly populate the element with all *Must Support* sub-elements for which a value is known. 
- AU PS Consumers **SHALL** handle the element if present and containing any *Must Support* sub-elements containing any valid value, and **SHOULD** display the value of this element (if the SHOULD:display Obligation is defined) when presenting the data to a human user.

For example, in the AU PS Practitioner Profile, the `name` element is labelled *Must Support* and has *Must Support* sub-elements `family` and `given`. When claiming conformance to this profile:
- AU PS Producers **SHALL** correctly populate a value in `Practitioner.name.family` and `Practitioner.name.given` if the value for those sub-elements is known.
- AU PS Consumers **SHALL** handle `Practitioner.name` if present and containing valid values in `Practitioner.name.family` and `Practitioner.name.given` sub-elements, and **SHOULD** display the value of at least the sub elements`Practitioner.name.family` and `Practitioner.name.given` when presenting the data to a human user.

##### Must Support - Resource References
Some elements labelled as *Must Support* reference multiple resource types or profiles such as `Observation.performer`. In such cases: 
- AU PS Producers **SHALL** correctly populate the element with at least one referenced resource or allowed profile if the value is known. 
- AU PS Consumers **SHALL** handle the element if present and containing any valid referenced resource or profiles, and **SHOULD** display the value of this element (if the SHOULD:display Obligation is defined) when presenting the data to a human user.

The table below provides a list of AU PS profile elements that allow multiple referenced resource types or profiles.

Profile |Must Support Element|Reference
---|---|---
[AU PS Composition](StructureDefinition-au-ps-composition.html)|Composition.author|AU PS Practitioner, AU PS PractitionerRole, Device, AU PS Patient, AU PS RelatedPerson, AU PS Organization
[AU PS Composition](StructureDefinition-au-ps-composition.html)|Composition.attester.party|AU PS Patient, AU PS RelatedPerson, AU PS Practitioner, AU PS PractitionerRole, AU PS Organization
[AU PS Composition](StructureDefinition-au-ps-composition.html)|Composition.section.entry:medicationStatementOrRequest|AU PS MedicationStatement, AU PS MedicationRequest
[DiagnosticReport (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DiagnosticReport-uv-ips.html)|DiagnosticReport.subject|AU PS Patient, Group
[DiagnosticReport (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DiagnosticReport-uv-ips.html)|DiagnosticReport.performer|AU PS Practitioner, AU PS PractitionerRole, AU PS Organization, CareTeam
[DiagnosticReport (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DiagnosticReport-uv-ips.html)|DiagnosticReport.result:observation-results|AU PS Pathology Result Observation, Observation Results - Radiology (IPS)
[AU PS Encounter](StructureDefinition-au-ps-encounter.html)|Encounter.participant.individual|AU PS Practitioner, AU PS PractitionerRole, AU PS RelatedPerson
[AU PS Encounter](StructureDefinition-au-ps-encounter.html)|Encounter.reasonReference|AU PS Condition, Observation, AU PS Procedure
[AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)|MedicationRequest.requester|AU PS Practitioner, AU PS PractitionerRole, AU PS Organization, AU PS Patient, AU PS RelatedPerson
[AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)|MedicationRequest.reasonReference|AU PS Condition, Observation
[AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)|MedicationStatement.reasonReference|AU PS Condition, Observation, DiagnosticReport (IPS)
[Observation Results - Radiology (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-results-radiology-uv-ips.html)|Observation.performer|AU PS Practitioner, AU PS PractitionerRole, AU PS Organization, CareTeam, AU PS Patient, AU PS RelatedPerson
[AU PS Patient](StructureDefinition-au-ps-patient.html)|Patient.generalPractitioner|AU PS Organization, AU PS Practitioner, AU PS PractitionerRole
[AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)|Observation.performer|AU PS Practitioner, AU PS PractitionerRole, AU PS Organization, AU PS Patient, AU PS RelatedPerson
[AU PS Procedure](StructureDefinition-au-ps-procedure.html)|Procedure.reasonReference|AU PS Condition, Observation, AU PS Procedure, DocumentReference
{:.grid}


##### Must Support - Choice of Data Types
Some elements labelled as *Must Support* allow different data types such as `Observation.effective[x]`. In such cases:
- AU PS Producers **SHALL** correctly populate the element with at least one data type allowed by the element definition if the value is known.
- AU PS Consumers **SHALL** handle the element if present and containing any valid data type allowed by the element definition, and **SHOULD** display the value of this element (if the SHOULD:display Obligation is defined) when presenting the data to a human user.

The table below provides a list of AU PS profile elements that allow multiple data types.

Profile |Must Support Element|Data Types
---|---|---
[AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)|AllergyIntolerance.onset[x]|dateTime, age, Period, Range
[AU PS Condition](StructureDefinition-au-ps-condition.html)|Condition.onset[x]|dateTime, age, Period, Range
[AU PS Condition](StructureDefinition-au-ps-condition.html)|Condition.abatement[x]|dateTime, age, Period, Range
[DeviceUseStatement (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DeviceUseStatement-uv-ips.html)|DeviceUseStatement.timing[x]|Period, dateTime
[DiagnosticReport (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DiagnosticReport-uv-ips.html)|DiagnosticReport.effective[x]|dateTime, Period
[AU PS Immunization](StructureDefinition-au-ps-immunization.html)|Immunization.occurrence[x]|dateTime, string
[AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)|MedicationRequest.medication[x]|CodeableConcept, Reference
[AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)|MedicationStatement.medication[x]|CodeableConcept, Reference
[AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)|MedicationStatement.effective[x]|dateTime, Period
[Observation Results - Radiology (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-results-radiology-uv-ips.html)|Observation.effective[x]|dateTime, Period
[Observation Results - Radiology (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-results-radiology-uv-ips.html)|Observation.value[x]|Quantity, CodeableConcept, string, boolean, integer, Range, Ratio, SampledData, time, dateTime, Period
[AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)|Observation.effective[x]|dateTime, Period,
[AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)|Observation.value[x]|Quantity, CodeableConcept, string, boolean, integer, Range, Ratio, SampledData, time, dateTime, Period
[AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)|Observation.component.value[x]|Quantity, CodeableConcept, string, boolean, integer, Range, Ratio, SampledData, time, dateTime, Period
[AU PS Procedure](StructureDefinition-au-ps-procedure.html)|Procedure.performed[x]|dateTime, Period, string, Age, Range
[DeviceUseStatement (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DeviceUseStatement-uv-ips.html)|DeviceUseStatement.timing[x]|Period, dateTime
{:.grid}

Some data type choices are labelled as *Must Support* and apply an additional obligation of [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). In such cases:
- AU PS Producers **SHOULD** be capable of correctly populating the element with this data type. Typically, this means that an application needs to demonstrate during some conformance testing process that there are some conditions under which it populates the element with a correct value. (i.e. not a data-absent-reason or equivalent.)

The table below provides a list of AU PS profile elements where a data type choice is labelled [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate).

Profile |Must Support Data Type
---|---
[AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)|AllergyIntolerance.onsetDateTime
[AU PS Condition](StructureDefinition-au-ps-condition.html)|Condition.onsetDateTime
[DeviceUseStatement (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DeviceUseStatement-uv-ips.html)|DeviceUseStatement.timingDateTime
[DiagnosticReport (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-DiagnosticReport-uv-ips.html)|DiagnosticReport.effectiveDateTime
[AU PS Immunization](StructureDefinition-au-ps-immunization.html)|Immunization.occurrenceDateTime
[AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)|MedicationStatement.effectiveDateTime
[Observation Results - Radiology (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-results-radiology-uv-ips.html)|Observation.effectiveDateTime
[AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)|Observation.effectiveDateTime
[AU PS Procedure](StructureDefinition-au-ps-procedure.html)|Procedure.performedDateTime
{:.grid}

##### Must Support - Choice of Identifiers 
A profile may support one or more than one identifier type and will include the supported identifiers in a profile by slicing the element and placing *Must Support* on each identifier slice. In such cases:
- AU PS Producers **SHALL**  correctly populate the element with identifiers from at least one supported identifier type where the identifier is known, or any known identifier when no supported identifier type is known.
- AU PS Consumers **SHALL** handle the element if present and containing any identifier type allowed by the element definition, and **SHOULD** display the value of each populated identifier when presenting the data to a human user.

The table below provides a list of AU PS profile elements that allow multiple identifier types.

Profile |Must Support Element|Supported Identifiers
---|---|---
[AU PS Organization](StructureDefinition-au-ps-organization.html)|Organization.identifier|HPI-O, Australian Business Number
[AU PS Patient](StructureDefinition-au-ps-patient.html)|Patient.identifier|IHI, Medicare Card Number, DVA Number
[AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)|Practitioner.identifier|HPI-I
[AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.html)|PractitionerRole.identifier|Medicare Provider Number
{:.grid}

For example, the profile [AU PS Patient](StructureDefinition-au-ps-patient.html) requires support for the following choices `Patient.identifier` defined in [AU Base Patient](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-patient.html) to support Individual Healthcare Identifier (IHI), Medicare Card Number, Department of Veterans' Affairs (DVA) Number. When claiming conformance to the AU PS Patient Profile:
- AU PS Producers **SHALL** correctly populate `Patient.identifier` with an IHI, or Medicare Card Number, or DVA Number, or any combination of them where the identifier is known, or any other identifier (e.g. Medical Record Number) when none of IHI, or Medicare Card Number, or DVA Number are known.
- AU PS Consumers **SHALL** handle `Patient.identifier` if present and containing any valid value. A valid value may be an IHI, Medicare Card Number, or DVA Number identifier, or may be some other allowed identifier. The AU PS Consumer **SHOULD** display the value of each populated identifier type (IHI, Medicare Number, DVA Number, or some other identifier) when presenting the data to a human user.

Systems **MAY** support populating other identifiers, but this is not a requirement of AU PS.

##### Must Support - Choice of Profile Elements

A resource may support two elements that are used to indicate a reason, e.g. `Encounter.reasonCode` and `Encounter.reasonReference` in the profile [AU PS Encounter](StructureDefinition-au-ps-encounter.html). In such cases:
- AU PS Producers **SHALL** correctly populate at least one element choice if the value is known.
- AU PS Consumers **SHALL** handle any element allowed by the profile if present and containing any valid value. 

The table below lists the applicable profiles and elements in AU PS.

Profile |Must Support Choice Elements
---|---
[AU PS Encounter](StructureDefinition-au-ps-encounter.html)|Encounter.reasonCode, Encounter.reasonReference
[AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)|MedicationRequest.reasonCode, MedicationRequest.reasonReference
[AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)|MedicationStatement.reasonCode, MedicationStatement.reasonReference
[AU PS Procedure](StructureDefinition-au-ps-procedure.html)|Procedure.reasonCode, Procedure.reasonReference
{:.grid}


##### Must Support - Choice of Terminology

In AU PS, elements that define support for more than one value set only apply to the [Coding](http://hl7.org/fhir/R4/datatypes.html#Coding) part of the element and are not intended to prevent systems from supplying only a text value. In such cases:
- AU PS Producers **SHALL** correctly populate the element with concepts from each supported value set where the applicable concept is known.
- AU PS Consumers **SHALL** handle the element if present and containing any valid value whether it is  from a supported value set or some other value set or text only, and **SHOULD** display the value of this element when presenting the data to a human user.

The table below lists the applicable profiles and elements in AU PS that support multiple value sets.

Profile |Must Support Sub-Element|Terminology Choices
---|---
[AU PS Immunization](StructureDefinition-au-ps-immunization.html)|Immunization.vaccineCode.coding|[Australian Medicines Terminology Vaccine](https://healthterminologies.gov.au/fhir/ValueSet/amt-vaccine-1), [Australian Immunisation Register Vaccine](https://healthterminologies.gov.au/fhir/ValueSet/australian-immunisation-register-vaccine-1)
[AU PS Medication](StructureDefinition-au-ps-medication.html)|Medication.code.coding|[Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1), [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html)
[AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)|MedicationRequest.code.coding|[Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1), [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html)
[AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)|MedicationStatement.code.coding|[Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1), [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html)
{:.grid}

For example, the profile [AU PS Medication](StructureDefinition-au-ps-medication.html) requires support for the following terminology choices `Medication.code.coding` defined in [AU Base Medication](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medication.html) to support [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) and [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html) as indicated by flagging *Must Support* on those two terminology slices.

When claiming conformance to the AU PS Medication profile: 
- AU PS Producers **SHALL** correctly populate `Medication.code.coding` with either a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, if a coded value is known. AU PS Producers **MAY** populate with only text if no coded value is known.
- AU PS Consumers **SHALL** handle `Medication.code.coding` if present and containing any valid value. A valid value may be text, or may be a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, or some other code. AU PS Consumers **SHOULD** display the value of this element when presenting the data to a human user.

Systems **MAY** populate other code systems but this is not a requirement of AU PS.