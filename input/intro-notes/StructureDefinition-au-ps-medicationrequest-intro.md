See [Comparison with other national and international IGs](comparison.html) for a comparison between AU Core profiles and profiles in other implementation guides.

### Profile specific implementation guidance
- See the [Medicine Information](https://build.fhir.org/ig/hl7au/au-fhir-core/medicine-information.html) page in AU Core for guidance on how medicinal product identification can be structured in FHIR conformant to AU Patient Summary.
- When recording "self-prescribed" medication, `MedicationRequest.requester` references the Patient or RelatedPerson as the prescriber.
- MedicationRequest resources can represent a medication using either a code with `MedicationRequest.medicationCodeableConcept`, or reference a [Medication](http://hl7.org/fhir/R4/medication.html) resource with `MedicationRequest.medicationReference`.
  - When referencing a Medication resource, it is preferred the resource is [contained](http://hl7.org/fhir/R4/references.html#contained) but it may be an external resource


<div class="stu-note">
This profile has been walked through, but conversion to derive from AU Core is delayed until the AU PS Encounter walk-through is complete, as referencing a dependent profile that has not yet been updated to derive from AU Core causes build errors.
</div>