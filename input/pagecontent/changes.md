###  Release TBD
- Publication date: TBD
- Publication status: TBD
- Based on FHIR version: 4.0.1

This change log documents the significant updates and resolutions implemented from version [0.3.0-ballot](https://hl7.org.au/fhir/ps/0.3.0-ballot/index.html) to TBD.

#### Changes in this version
- [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html):
  - removed SHOULD:display obligation on AllergyIntolerance.patient.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
- [AU PS Composition](StructureDefinition-au-ps-composition.html):
  - changed Composition.section[all slices].code cardinality from 0..1 to 1..1, and added Must Support and obligation SHALL:handle for the AU PS Consumer [IPS: FHIR-51231](https://jira.hl7.org/browse/FHIR-51231)
  - changed Composition.section.code to remove use of the CodableConceptIPS [IPS: FHIR-51231](https://jira.hl7.org/browse/FHIR-51231)
  - removed the cardinality constraint on Composition.section[all slices].extension:section-note, changing it from 0..1 to 0..* [IPS: FHIR-50271](https://jira.hl7.org/browse/FHIR-50271)
  - removed SHOULD:display obligation on Composition.identifier, Composition.type, and Composition.subject.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
  - changed Composition.section[all slices].title and Composition.section[all slices].text obligations from SHALL:populate-if-known to SHALL:populate for the AU PS Producer [IPS: FHIR-51259](https://jira.hl7.org/browse/FHIR-51259)
- [AU PS Condition](StructureDefinition-au-ps-condition.html):
  - changed Condition.bodySite to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
  - removed SHOULD:display obligation on Condition.subject.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
- [AU PS Immunization](StructureDefinition-au-ps-immunization.html):
  - changed Immunization.site and Immunization.route to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
  - removed SHOULD:display obligation on Immunization.patient.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
- [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html):
  - changed MedicationRequest.dosageInstruction.route to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
  - changed MedicationRequest.doNotPerform to constrain out 'true' [IPS: FHIR-51483](https://jira.hl7.org/browse/FHIR-51483)
  - removed SHOULD:display obligation on MedicationRequest.subject.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
- [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html):
  - changed MedicationStatement.dosage.route to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
  - removed SHOULD:display obligation on MedicationStatement.subject.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
- [AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html):
  - changed Observation.interpretation to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
  - removed SHOULD:display obligation on Observation.subject.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
- [AU PS Patient](StructureDefinition-au-ps-patient.html):
  - changed Patient.contact.relationship to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
- [AU PS Procedure](StructureDefinition-au-ps-procedure.html):
  - changed Procedure.bodySite to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
  - removed SHOULD:display obligation on Procedure.subject.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
- [AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.html):
  - changed Observation.valueCodeableConcept to remove use of the CodableConceptIPS [IPS: FHIR-51257](https://jira.hl7.org/browse/FHIR-51257)
  - removed SHOULD:display obligation on Observation.subject.reference for the AU PS Consumer [IPS: FHIR-51258](https://jira.hl7.org/browse/FHIR-51258)
