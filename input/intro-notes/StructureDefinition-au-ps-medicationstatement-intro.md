{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- See the [Medicine Information](https://build.fhir.org/ig/hl7au/au-fhir-core/medicine-information.html) page in AU Core for guidance on how medicinal product identification can be structured in FHIR conformant to AU Patient Summary.
- MedicationStatement resources can represent a medication using either a code with `MedicationStatement.medicationCodeableConcept`, or reference a [Medication](http://hl7.org/fhir/R4/medication.html) resource with `MedicationStatement.medicationReference`.
  - When referencing a Medication resource, it is preferred the resource is [contained](http://hl7.org/fhir/R4/references.html#contained) but it may be an external resource