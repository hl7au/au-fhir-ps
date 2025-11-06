{% include comparison-note-boilerplate.md %}


### Profile Specific Implementation Guidance
- See the [guidance on implementing the Medication resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medication.html#profile-specific-implementation-guidance) in AU Core.
- When populating `Medication.code` producers **SHALL** correctly populate `Medication.code.coding` with either a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, if a coded value is known and **MAY** populate with a code from another code system.
  - Producers **MAY** populate with only text if no coded value is known.
- The Medication resource **SHALL NOT** be used to represent that a patient is not currently taking any medications; systems **SHOULD** use the MedicationStatement following the [profile specific implementation guidance in AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html#profile-specific-implementation-guidance).