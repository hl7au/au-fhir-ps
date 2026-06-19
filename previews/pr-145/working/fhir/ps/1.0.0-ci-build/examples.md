# Examples - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* **Examples**

## Examples

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

The following examples are published with this guide and all are available as a downloadable as zip file [here](downloads.md#examples).

These example instances show what data produced and consumed by systems conforming with this implementation guide might look like. Every effort has been made to ensure that the examples are correct and useful, but they are not a normative part of the specification nor are they fully representative of real world examples.

In addition to the examples defined in this implementation guide, synthetic (realistic but not real) test data for developers and testers that conforms to HL7 Australia FHIR implementation guides is maintained in the [HL7 AU FHIR Test Data](https://github.com/hl7au/au-fhir-test-data) repository.

### AU PS Bundle Examples

The examples included in this guide are AU PS documents (i.e. Bundles); standalone examples of AU PS profiles are not provided.

A set of examples are provided to demonstrate some parts of AU PS profiles (e.g. `Composition.section.emptyReason`, No Known X, Data Absent Reason extension) but are not intended to demonstrate clinical workflows or use cases:

* [Basic Summary](Bundle-aups-basicsummary.md)
* [No Known X](Bundle-aups-noknownx.md)
* [Section empty reason](Bundle-aups-section-emptyreason.md)

A set of examples demonstrate technical and clinical use case aspects, conforming to the AU PS requirements. Data within the use cases examples (e.g. medications) is provided by the [Sparked Patient Summary Clinical Focus Group](https://sparked.csiro.au/index.php/design-groups/):

* [Jeramy 27 May](Bundle-aups-gpvisit-retrieval.md)
* [Joyce 28 October](Bundle-aups-referral-endoconsult-curated.md)
* [Joyce 07 November 2024](Bundle-aups-referral-endoconsult-autogen.md)

The table below identifies some major characteristics of the examples defined in this IG, e.g. the profile a section entry or Composition element is populated with.

| | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Use Case** | - | - | - | [Interstate GP Visit](uc-interstate.md) | [Referral to Specialist and Allied Health](uc-referral.md) | [Referral to Specialist and Allied Health](uc-referral.md) |
| `Composition.author` | AU PS PractitionerRole | AU PS PractitionerRole | AU PS RelatedPerson | AU PS Practitioner | AU PS PractitionerRole | Device |
| `Composition.attester` | - | - | - | - | AU PS PractitionerRole | - |
| `Composition.section:sectionProblems` | AU PS Condition | AU PS Condition | emptyReason | AU PS Condition | AU PS Condition | AU PS Condition |
| `Composition.section:sectionAllergies` | AU PS AllergyIntolerance | AU PS AllergyIntolerance | emptyReason | AU PS AllergyIntolerance | AU PS AllergyIntolerance | AU PS AllergyIntolerance |
| `Composition.section:sectionMedications` | AU PS MedicationStatement | AU PS MedicationStatement | emptyReason | AU PS MedicationRequest | AU PS MedicationStatement | AU PS MedicationStatement |
| `Composition.section:sectionImmunizations` | - | - | emptyReason | AU PS Immunization | AU PS Immunization | AU PS Immunization |
| `Composition.section:sectionResults` | - | - | - | AU PS Pathology Result | - | AU PS Pathology Result |
| `Composition.section:sectionProceduresHx` | - | - | - | AU PS Procedure | - | - |
| `Composition.section:sectionMedicalDevices` | - | - | - | - | - | - |
| `Composition.section:sectionAdvanceDirectives` | - | - | - | - | - | - |
| `Composition.section:sectionAlerts` | - | - | - | - | - | - |
| `Composition.section:sectionFunctionalStatus` | - | - | - | - | - | - |
| `Composition.section:sectionPastProblems` | - | - | - | - | - | AU PS Condition |
| `Composition.section:sectionPregnancyHx` | - | - | - | - | Pregnancy - Status (IPS) | Pregnancy - Status (IPS) |
| `Composition.section:sectionPatientStory` | - | - | - | - | - | - |
| `Composition.section:sectionPlanOfCare` | - | - | - | - | - | - |
| `Composition.section:sectionSocialHistory` | - | - | - | - | AU PS Smoking Status | AU PS Smoking Status |
| `Composition.section:sectionVitalSigns` | - | - | - | - | - | - |
| `Bundle.signature.who` | - | - | - | - | PractitionerRole | Device |

#### Missing Data, Empty Sections, Known Absence of Data, No Known X and Suppressed Data

The table below indicates the elements within examples that demonstrate aspects of [Missing Data, Empty Sections, Known Absence of Data, No Known X](general-requirements.md#missing-data-empty-sections-known-absence-of-data-no-known-x).

| | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Missing Data** | - | - | `Patient.birthDate` | `MedicationRequest.authoredOn` | - | `Observation.performer` |
| `Immunization.occurrenceDateTime` | | | | | | |
| `Observation.performer` | | | | | | |
| **Empty Sections** | - | - | `Composition.section:sectionProblems` | - | - | - |
| `Composition.section:sectionAllergies` | | | | | | |
| `Composition.section:sectionMedications` | | | | | | |
| `Composition.section:sectionImmunizations` | | | | | | |
| **Known Absence of Data Due to Workflow** | - | - | - | - | - | - |
| **No Known X** | `Condition.code` | `AllergyIntolerance.code` | - | `AllergyIntolerance.code` | `AllergyIntolerance.code` | - |
| `MedicationStatement.medicationCodeableConcept` | | | | | | |
| `Condition.code` | | | | | | |
| **Suppressed Data** | - | - | `Patient.identifier` | - | - | - |
| `Patient.gender` | | | | | | |

