<div class="note-to-balloters" markdown="1">
**Upcoming NCTS ValueSet Availability**

Balloters should note that AU Base has submitted a request to NCTS to add a specific value set with agreed changed terminology defined for binding to <code>AllergyIntolerance.reaction.manifestation</code>. This request is pending release and the value set is not available in this guide at the time of publishing.

Balloters should consider the content of the <a href="https://www.healthterminologies.gov.au/integration/R4/fhir/ValueSet/sctau-reference-set-142341000036103">indicative reference set</a> available now that the new NCTS ValueSet will be based on.

Related JIRA issue with details is <a href="https://jira.hl7.org/browse/FHIR-47076">AU Base: FHIR-47076</a>.

**Ongoing IPS 2.0.0 Work**

The content of this release of AU PS is based on the currently approved set of changes for IPS 2.0.0 as of 4 August 2025. Work on IPS 2.0.0 is ongoing and as such changes approved post publication of this release are expected on this profile. The [CI Build for IPS](https://build.fhir.org/ig/HL7/fhir-ips/) pre-applies the latest proposed changes, and can be used as a reference for potential changes to AU PS that will be inherited from IPS 2.0.0. [IPS Block Vote 12](https://jira.hl7.org/issues/?jql=project%20%3D%20FHIR%20AND%20Specification%20~%20%22International%20Patient%20Summary%22%20AND%20createdDate%20%3E%202023-01-01%20AND%20cf%5B11402%5D%20%3D%20Block-Vote-12) and [IPS Block Vote 13](https://jira.hl7.org/issues/?jql=project%20%3D%20FHIR%20AND%20Specification%20~%20%22International%20Patient%20Summary%22%20AND%20createdDate%20%3E%202023-01-01%20AND%20cf%5B11402%5D%20%3D%20Block-Vote-13) can be referred to for a list of the remaining IPS 2.0.0 changes to be approved.
</div>

{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the AllergyIntolerance resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html#profile-specific-implementation-guidance) in AU Core.

<div class="stu-note" markdown="1">

The additional obligation on `AllergyIntolerance.onsetDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the profile view. See [Zulip discussion](https://chat.fhir.org/#narrow/channel/179252-IG-creation/topic/Obligation.20Extension.20on.20ElementDefinition.2Etype.20not.20rendering) for more information.

</div><!-- stu-note -->