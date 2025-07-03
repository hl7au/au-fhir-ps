{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- See the [guidance on implementing the Patient resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-patient.html#profile-specific-implementation-guidance) in AU Core.
- When populating `Patient.identifier`, producers are not required to populate all known patient identifiers from the source system. Producers:
  - **SHALL** populate with at least one identifier
  - **SHALL** populate with at least one of the supported identifier types if known
  - **SHOULD** populate an IHI in preference to Medicare or DVA numbers where the IHI is known and **MAY** also provide a Medicare, DVA number, other identifier type or any combination of them