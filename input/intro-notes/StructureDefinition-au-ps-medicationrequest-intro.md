{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the MedicationRequest resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationrequest.html#profile-specific-implementation-guidance) in AU Core.
- When populating `MedicationRequest.medicationCodeableConcept` producers **SHALL** correctly populate `MedicationRequest.medicationCodeableConcept.coding` with either a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, if a coded value is known and **MAY** populate with a code from another code system.
  - Producers **MAY** populate with only text if no coded value is known.
- The MedicationRequest resource can represent the clinical indication as a code with `MedicationRequest.reasonCode`, or a reference with `MedicationRequest.reasonReference` to a Condition or other resource.
  - Although both are marked as *Must Support*, producers are not required to support both a code and a reference, but they **SHALL** support *at least one* of these elements
  - A consumer **SHALL** support both elements  