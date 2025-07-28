{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- See the [guidance on implementing the Condition resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html#profile-specific-implementation-guidance) in AU Core.
- Implementers populating a bundle entry with an unprofiled resoure type, e.g. MedicationAdministration, are recommended to consider the corresponding [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/) profile, e.g. [AU Base MedicationAdministration](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medicationadministration.html), as guidance for that resource type in an Australian healthcare context.

