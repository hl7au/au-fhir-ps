{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the Immunization resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-immunization.html#profile-specific-implementation-guidance) in AU Core.
- When populating `Immunization.vaccineCode` producers **SHALL** correctly populate `Immunization.vaccineCode.coding` with either a code from [Australian Medicines Terminology Vaccine](https://healthterminologies.gov.au/fhir/ValueSet/amt-vaccine-1) or [Australian Immunisation Register Vaccine](https://healthterminologies.gov.au/fhir/ValueSet/australian-immunisation-register-vaccine-1), or both, if a coded value is known and **MAY** populate with a code from another code system.
  - Producers **MAY** populate with only text if no coded value is known.

<div class="stu-note" markdown="1">

The additional obligation on `Immunization.occurrenceDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the Formal Views of Profile Content. See [Zulip discussion](https://chat.fhir.org/#narrow/channel/179252-IG-creation/topic/Obligation.20Extension.20on.20ElementDefinition.2Etype.20not.20rendering) for more information.

</div><!-- stu-note -->
