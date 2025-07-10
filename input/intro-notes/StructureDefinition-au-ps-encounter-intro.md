{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- See the [guidance on implementing the Encounter resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-encounter.html#profile-specific-implementation-guidance) in AU Core.
- The Encounter resource can represent a clinical indication with `Encounter.reasonCode`, or a reference with `Encounter.reasonReference` to a Condition or other resource.
  - Although both are marked as *Must Support*, producers are not required to support both a code and a reference, but they **SHALL** support *at least one* of these elements
  - A consumer **SHALL** support both elements
