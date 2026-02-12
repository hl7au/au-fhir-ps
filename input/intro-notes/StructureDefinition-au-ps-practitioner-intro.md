{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- Even though AU PS Profiles allow both PractitionerRole and Practitioner to be referenced, because PractitionerRole supplies a provider’s location, contact information, and reference to the Practitioner, it **SHOULD** be referenced instead of the Practitioner resource. 
- See the [guidance on implementing the Practitioner resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-practitioner.html#profile-specific-implementation-guidance) in AU Core.

**Examples for this Profile**: [Bundle/aups-basicsummary](Bundle-aups-basicsummary.html), [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.html), [Bundle/aups-noknownx](Bundle-aups-noknownx.html), [Bundle/aups-referral-endoconsult-autogen](Bundle-aups-referral-endoconsult-autogen.html) and [Bundle/aups-referral-endoconsult-curated](Bundle-aups-referral-endoconsult-curated.html)
