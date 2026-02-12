{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the Patient resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-patient.html#profile-specific-implementation-guidance) in AU Core.
- When populating `Patient.identifier`, producers are not required to populate all known patient identifiers from the source system. Producers:
  - **SHALL** populate with at least one identifier
  - **SHALL** populate with at least one of the supported identifier types if known
  - **SHOULD** populate an IHI in preference to Medicare or DVA numbers where the IHI is known and **MAY** also provide a Medicare, DVA number, other identifier type or any combination of them
- This profile supports the sex, gender, and related concepts of: Name to Use, Gender Identity, and Individual Pronouns. See the [Sex and Gender](sex-and-gender.html) page for guidance on exchanging sex and gender related concepts conformant to AU PS.

**Examples for this Profile**: [Bundle/aups-basicsummary](Bundle-aups-basicsummary.html), [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.html), [Bundle/aups-noknownx](Bundle-aups-noknownx.html), [Bundle/aups-referral-endoconsult-autogen](Bundle-aups-referral-endoconsult-autogen.html), [Bundle/aups-referral-endoconsult-curated](Bundle-aups-referral-endoconsult-curated.html) and [Bundle/aups-section-emptyreason](Bundle-aups-section-emptyreason.html)