{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the Procedure resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html#profile-specific-implementation-guidance) in AU Core.
- The Procedure resource can represent a clinical indication with `Procedure.reasonCode`, or a reference with `Procedure.reasonReference` to a Condition or other resource.
  - Although both are marked as *Must Support*, producers are not required to support both a code and a reference, but they **SHALL** support *at least one* of these elements
  - A consumer **SHALL** support both elements

<div class="stu-note" markdown="1">

The additional obligation on `Procedure.performedDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the Formal Views of Profile Content. See [Zulip discussion](https://chat.fhir.org/#narrow/channel/179252-IG-creation/topic/Obligation.20Extension.20on.20ElementDefinition.2Etype.20not.20rendering) for more information.

</div><!-- stu-note -->

**Examples for this Profile**: [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.html)