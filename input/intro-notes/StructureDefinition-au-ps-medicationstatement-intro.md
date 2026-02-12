{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the MedicationStatement resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html#profile-specific-implementation-guidance) in AU Core.
- When populating `MedicationStatement.medicationCodeableConcept` producers **SHALL** correctly populate `MedicationStatement.medicationCodeableConcept.coding` with either a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, if a coded value is known and **MAY** populate with a code from another code system.
  - Producers **MAY** populate with only text if no coded value is known.
- The MedicationStatement resource can represent the clinical indication as a code with `MedicationStatement.reasonCode`, or a reference with `MedicationStatement.reasonReference` to a Condition or other resource.
   - Although both are marked as *Must Support*, producers are not required to support both a code and a reference, but they **SHALL** support *at least one* of these elements
   - A consumer **SHALL** support both elements 
- To represent that a patient is not currently taking any medications, the code SNOMED CT 1234391000168107 &#124;No known current medicines&#124; is used in `MedicationStatement.medicationCodeableConcept`:
  - `MedicationStatement.status` is set to "active"
  - `MedicationStatement.effectiveDateTime` is the date/time the statement was current
  - A Medication resource referenced in `MedicationStatement.medicationReference` **SHALL NOT** be used
  - Implementers need to be aware than an IPS document conforming to 1.0.0 or 1.1.0 may provide instead the IPS preferred concept ["no-known-medications"](https://hl7.org/fhir/uv/ips/STU1/CodeSystem-absent-unknown-uv-ips.html#absent-unknown-uv-ips-no-known-medications) or if conforming to 2.0.0 may provide instead the IPS preferred concept 787481004 &#124;No known medications&#124;. The IPS concept ["no-known-medications"](https://hl7.org/fhir/uv/ips/STU1/CodeSystem-absent-unknown-uv-ips.html#absent-unknown-uv-ips-no-known-medications) has been removed from later versions of IPS and the  the SNOMED CT code 787481004 &#124;No known medications&#124; is currently inactive in SNOMED CT-AU. These concepts **SHOULD NOT** be used when producing AU PS compliant data, but receiving systems may still encounter it in IPS documents. 

<div class="stu-note" markdown="1">

The additional obligation on `MedicationStatement.effectiveDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.html) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the Formal Views of Profile Content. See [Zulip discussion](https://chat.fhir.org/#narrow/channel/179252-IG-creation/topic/Obligation.20Extension.20on.20ElementDefinition.2Etype.20not.20rendering) for more information.

</div><!-- stu-note -->

**Examples for this Profile**: [Bundle/aups-basicsummary](Bundle-aups-basicsummary.html), [Bundle/aups-noknownx](Bundle-aups-noknownx.html), [Bundle/aups-referral-endoconsult-autogen](Bundle-aups-referral-endoconsult-autogen.html) and [Bundle/aups-referral-endoconsult-curated](Bundle-aups-referral-endoconsult-curated.html)