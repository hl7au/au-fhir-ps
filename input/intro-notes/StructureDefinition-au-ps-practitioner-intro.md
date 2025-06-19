{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- Even though AU Patient Summary Profiles allow both PractitionerRole and Practitioner to be referenced, because PractitionerRole supplies a provider’s location, contact information, and reference to the Practitioner, it **SHOULD** be referenced instead of the Practitioner resource. 
- See the [guidance on implementing the Practitioner resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-practitioner.html#profile-specific-implementation-guidance) in AU Core.


