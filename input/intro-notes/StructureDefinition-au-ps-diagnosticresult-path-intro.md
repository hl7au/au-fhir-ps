{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- See the [guidance on implementing the pathology result Observation resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-diagnosticresult-path.html#profile-specific-implementation-guidance) in AU Core.
- When implementing support for specimen information, the conformance expectations of the [Specimen (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Specimen-uv-ips) profile **SHALL** be met.

<div class="stu-note" markdown="1">

1. The additional obligation on `Observation.effectiveDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the profile view. See [Zulip discussion](https://chat.fhir.org/#narrow/stream/179252-IG-creation/topic/Obligation.20on.20ElementDefinition.2Etype) for more information.

2. There is a current tool limitation that prevents the Observation.specimen element referencing the intended target profile: [Specimen (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Specimen-uv-ips).

</div><!-- stu-note -->