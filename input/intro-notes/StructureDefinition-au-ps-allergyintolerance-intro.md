<div class="note-to-balloters" markdown="1">
**Upcoming NCTS ValueSet Availability**

Balloters should note that AU Base has submitted a request to NCTS to add a specific value set with agreed changed terminology defined for binding to <code>AllergyIntolerance.reaction.manifestation</code>. This request is pending release and the value set is not available in this guide at the time of publishing.

Balloters should consider the content of the <a href="https://www.healthterminologies.gov.au/integration/R4/fhir/ValueSet/sctau-reference-set-142341000036103">indicative reference set</a> available now that the new NCTS ValueSet will be based on.

Related JIRA issue with details is <a href="https://jira.hl7.org/browse/FHIR-47076">AU Base: FHIR-47076</a>.
</div>

{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the AllergyIntolerance resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html#profile-specific-implementation-guidance) in AU Core.

<div class="stu-note" markdown="1">

The additional obligation on `AllergyIntolerance.onsetDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the profile view. See [Zulip discussion](https://chat.fhir.org/#narrow/stream/179252-IG-creation/topic/Obligation.20on.20ElementDefinition.2Etype) for more information.

</div><!-- stu-note -->