# Comparison With Other National and International IGs - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**Guidance**](guidance.md)
* **Comparison With Other National and International IGs**

## Comparison With Other National and International IGs

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

AU Patient Summary (AU PS) complies with, and/or leverages, national and international standards, in particular:

* [International Patient Access 1.1.0](https://hl7.org/fhir/uv/ipa/STU1.1/)
* [International Patient Summary Implementation Guide 2.0.0](https://hl7.org/fhir/uv/ips/STU2/)
* [AU Core Implementation Guide 2.0.0](https://build.fhir.org/ig/hl7au/au-fhir-core/)

Relationships between AU PS, AUCDI, and the above key implementation guides are described in [Relationship with other IGs](relationship.md).

### Profile Comparison

As part of profile comparison, the requirements, constraints, and standards specified in a particular FHIR profile are evaluated. These requirements can include mandatory elements, **Must Support** elements, cardinality constraints, data types, terminology bindings, usage rules, extensions, rules on missing or suppressed data.

The table below provides a profile only comparison from AU PS to profiles in key implementation guides. Compliance in the reverse direction is not guaranteed, i.e. a resource that is compliant with an International Patient Summary profile **MAY NOT** be compliant with AU PS.

The comparison considers **SHALL** and **SHOULD** requirements. **MAY** requirements are not compared.

**Legend:**

![](green_checkmark.png) **Compliant**: An AU PS compliant resource meets all requirements of the compared profile.

![](orange_checkmark.png) **Additional requirements**: An AU PS compliant resource is compatible, but additional changes may be needed to meet all requirements of the compared profile. Where additional requirements are identified, more information is provided in the sections below.

![](cross_red_circle.png) **Incompatible**: An AU PS compliant resource is incompatible with the compared profile. A resource cannot be compliant to both. Where incompatible requirements are identified, more information is provided in the sections below.

![](minus_symbol.png) **No equivalent profile**: No equivalent profile for comparison.

| | | | |
| :--- | :--- | :--- | :--- |
| [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS Bundle](StructureDefinition-au-ps-bundle.md) | ![](minus_symbol.png) | ![](green_checkmark.png) | ![](minus_symbol.png) |
| [AU PS Composition](StructureDefinition-au-ps-composition.md) | ![](minus_symbol.png) | ![](green_checkmark.png) | ![](minus_symbol.png) |
| [AU PS Condition](StructureDefinition-au-ps-condition.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| IPA-problem-list-item![](orange_checkmark.png) | | | |
| [AU PS Encounter](StructureDefinition-au-ps-encounter.md) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](green_checkmark.png) |
| [AU PS Immunization](StructureDefinition-au-ps-immunization.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS Medication](StructureDefinition-au-ps-medication.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.md) | ![](orange_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md) | ![](orange_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS Organization](StructureDefinition-au-ps-organization.md) | ![](minus_symbol.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS Patient](StructureDefinition-au-ps-patient.md) | ![](orange_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS Practitioner](StructureDefinition-au-ps-practitioner.md) | ![](orange_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS Procedure](StructureDefinition-au-ps-procedure.md) | ![](minus_symbol.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |
| [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.md) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](green_checkmark.png) |
| [AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) |

#### IPA Profile Additional Requirements

The following IPA profile(s) contain additional requirements. Implementers are advised to note that some code changes may be required to support these profiles.

| | | | |
| :--- | :--- | :--- | :--- |
| [AU PS Condition](StructureDefinition-au-ps-condition.md) | [IPA-problem-list-item](https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-problem-list-item.html) | Condition.category | Requires category of 'problem-list-item'. |
| [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.md) | [IPA-MedicationRequest](https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-medicationrequest.html) | MedicationRequest.reported[x] | *Must Support*element in IPA. |
| [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md) | [IPA-MedicationStatement](https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-medicationstatement.html) | MedicationStatement.statusReason | *Must Support*element in IPA. |
| MedicationStatement.context | *Must Support*element in IPA. | | |
| MedicationStatement.informationSource | *Must Support*element in IPA. | | |
| [AU PS Patient](StructureDefinition-au-ps-patient.md) | [IPA-Patient](https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-patient.html) | Patient.identifier | IPA requires all identifiers to have value (1..1), and at least one of system, type or assigner (ipa-pat-1). |
| Patient.identifier.value | *Must Support*element in IPA. | | |
| Patient.active | Element SHOULD be present if Patient.link is present (ipa-pat-4).*Must Support*element in IPA. | | |
| Patient.name.text | Sub-element SHOULD be present (ipa-pat-3). | | |
| Patient.link | *Must Support*element in IPA. | | |
| [AU PS Practitioner](StructureDefinition-au-ps-practitioner.md) | [IPA-Practitioner](https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-practitioner.html) | Practitioner.name.text | Sub-element SHOULD be present (ipa-pract-1). |

##### Missing and Suppressed Data

AU PS compliant resources are compliant with IPA requirements for Missing Data. IPA does not include requirements for Suppressed Data.

##### Additional Profiles

This version of AU PS has no equivalent profile for the following IPA profiles:

* IPA-DocumentReference

### Capability Statement Comparison

No comparison is undertaken. AU PS does not define any FHIR specific interactions - no CapabilityStatement is defined.

Systems implementing AU Patient Summary **MAY** implement interactions defined in other CapabilityStatements, for example:

* [IPS Server Capability Statement](https://hl7.org/fhir/uv/ips/STU2/CapabilityStatement-ips-server.html)
* [International Patient Access Server CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-server.html)
* [International Patient Access Client CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-client.html)

