# Profiles and Extensions - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* **Profiles and Extensions**

## Profiles and Extensions

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

### Profiles

The following profiles have been defined for this implementation guide.

#### AllergyIntolerance

* [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.md)

#### Bundle

* [AU PS Bundle](StructureDefinition-au-ps-bundle.md)

#### Composition

* [AU PS Composition](StructureDefinition-au-ps-composition.md)

#### Condition

* [AU PS Condition](StructureDefinition-au-ps-condition.md)

#### Encounter

* [AU PS Encounter](StructureDefinition-au-ps-encounter.md)

#### Immunization

* [AU PS Immunization](StructureDefinition-au-ps-immunization.md)

#### Medication

* [AU PS Medication](StructureDefinition-au-ps-medication.md)

#### MedicationRequest

* [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.md)

#### MedicationStatement

* [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)

#### Observation

* [AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.md)
* [AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.md)

#### Organization

* [AU PS Organization](StructureDefinition-au-ps-organization.md)

#### Patient

* [AU PS Patient](StructureDefinition-au-ps-patient.md)

#### Practitioner

* [AU PS Practitioner](StructureDefinition-au-ps-practitioner.md)

#### PractitionerRole

* [AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.md)

#### Procedure

* [AU PS Procedure](StructureDefinition-au-ps-procedure.md)

#### RelatedPerson

* [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.md)

#### Other Profiles Used

In addition to the profiles defined in this implementation guide, the following profiles defined elsewhere are used by AU Patient Summary. These profiles are a data type profile for a **Must Support** element in an AU PS profile or are the target of a **Must Support** reference element in an AU PS profile through definition or by impose:

* [AU Australian Business Number](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-australianbusinessnumber.html)
* [AU Base Dosage](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-dosage.html)
* [AU Core Location](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-location.html)
* [AU DVA Number](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-dvanumber.html)
* [AU HPI-I](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-hpii.html)
* [AU HPI-O](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-hpio.html)
* [AU IHI](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-ihi.html)
* [AU Medicare Card Number](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medicarecardnumber.html)
* [AU Medicare Provider Number](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medicareprovidernumber.html)
* [Codeable Concept (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-CodeableConcept-uv-ips.html)
* [Device (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Device-uv-ips.html)
* [DeviceUseStatement (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-DeviceUseStatement-uv-ips.html)
* [DiagnosticReport (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-DiagnosticReport-uv-ips.html)
* [Observation Results - Radiology (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-results-radiology-uv-ips.html)

Additional IPS profiles are referenced in [AU PS Bundle](StructureDefinition-au-ps-bundle.md) and [AU PS Composition](StructureDefinition-au-ps-composition.md), but are not labelled **Must Support** in AU PS (or IPS).

### Extensions

All extensions used in this guide are defined in the FHIR Extensions Pack or [AU Base](http://build.fhir.org/ig/hl7au/au-fhir-base/profiles-and-extensions.html#extensions).

The following extensions are marked with **Must Support** in this implementation guide:

* [Australian Indigenous Status](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-indigenous-status.html) in [AU PS Patient](StructureDefinition-au-ps-patient.md)
* [Individual Pronouns](https://hl7.org/fhir/extensions/5.1.0/StructureDefinition-individual-pronouns.html) in [AU PS Patient](StructureDefinition-au-ps-patient.md)
* [Individual Gender Identity](https://hl7.org/fhir/extensions/5.1.0/StructureDefinition-individual-genderIdentity.html) in [AU PS Patient](StructureDefinition-au-ps-patient.md)

