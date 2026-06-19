# AUCDI - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**Guidance**](guidance.md)
* **AUCDI**

## AUCDI

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

[Australian Clinical Data for Interoperability (AUCDI)](https://sparked.csiro.au/index.php/sparked-products-resources/aucdi/) and AU Patient Summary (AU PS) complement each other assisting in common understanding of clinical data concepts when implemented in systems and exchanged between systems.

AUCDI defines data groups comprising one or more data elements and references clinical terminology concepts, forming the foundation of a common language to allow systems to exchange semantically accurate data more efficiently. AUCDI defines clinical requirements for the data required to support the provision of care, exchange, aggregation for analysis, and to support clinical decision support. AUCDI may define requirements that are future focussed and as yet do not align with system implementation of the clinical concept.

AU PS is a technical specification that addresses constraints and obligations on data representation for generation, exchange, and consumption of patient summaries in the Australian healthcare context. AU PS enables system data to be mapped to an agreed FHIR format for systems in Australia.

**Figure 1: AUCDI and AU PS development approach** 


An interpretation of AUCDI clinical information requirements through community consensus is undertaken to define support for the exchange of clinical and administrative data within technical constraints. Note that:

* In any particular release, AU Core or AU PS may not cover all AUCDI data concepts, especially when AUCDI data concepts are not supported in existing systems.
* AU PS includes exchange for concepts that are commonly implemented in systems and not included in AUCDI e.g. `Patient.name`, `Practitioner.identifier`, `Procedure.encounter`.
* AU PS includes exchange for clinical concepts not yet included in AUCDI, e.g. MedicationRequest, which are included through reference to IPS or AU Core.
* AU PS includes data elements not included in AUCDI that are required to make FHIR implementable e.g. `Observation.status`, `MedicationRequest.intent`.

### AUCDI and AU PS Versions

AUCDI R2 builds upon R1, expanding on the initial “core”, introducing additional data groups to support different use cases including "Patient summary":

| | |
| :--- | :--- |
| R1 | - |
| R2 (Patient summary) | 1.0.0 |

### AUCDI (Patient summary) Mappings Into AU PS

The table below shows the relationship between data defined in the "Patient summary" AUCDI Data Groups and Elements, AU Core profiles, and AU PS profiles.

Column attribute descriptions are as follows:

* **AUCDI Data Group**: The name of the AUCDI data group.
* **AUCDI Data Element**: The name of the AUCDI data element within an AUCDI data group.
* **AU PS Document Section**: The AU PS Document section relevant for exchange (see [Structure of the Australian Patient Summary (AU PS)](the-aups.md#structure-of-the-au-ps)).
* **AU PS Profile(s)**: The title of the AU PS profile relevant for exchange.
* **FHIR Path**: The [FHIRPath expression](https://build.fhir.org/ig/HL7/FHIRPath/) to the FHIR element relevant for exchange, i.e. the FHIR element that can be populated with data from a source system that represents the clinical concept expressed in the AUCDI data element.
* **Comment**: Additional information about the mapping including an explanation of where an element or group is not yet mapped.

* AUCDI Data Group: Adverse reaction risk summary
  * AUCDI Data Element: Substance name
  * AU PS Document Section: Allergies and Intolerances
  * IPS Profile(s): [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.md)
  * FHIR Path: `AllergyIntolerance.code`
  * Comment: 
* AUCDI Data Group: Date/time of onset of first reaction
  * AUCDI Data Element: [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.md)
  * AU PS Document Section: `AllergyIntolerance.onset[x]`
  * IPS Profile(s): This AUCDI element aligns with the first identification of an allergy or intolerance. The onset value may be patient reported or clinically determined; estimated or actual; age or date and be imprecise (partial date), range of ages or a period of time.
* AUCDI Data Group: Manifestation
  * AUCDI Data Element: [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.md)
  * AU PS Document Section: `AllergyInterolance.reaction`
  * IPS Profile(s): 
* AUCDI Data Group: Severity of reaction
  * AUCDI Data Element: [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.md)
  * AU PS Document Section: `AllergyIntolerance.reaction.severity`
  * IPS Profile(s): 
* AUCDI Data Group: Comment
  * AUCDI Data Element: [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.md)
  * AU PS Document Section: `AllergyIntolerance.note`
  * IPS Profile(s): 
* AUCDI Data Group: Last updated
  * AUCDI Data Element: -
  * AU PS Document Section: -
  * IPS Profile(s): This AUCDI element is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Last Menstrual Period (LMP) assertion
  * AUCDI Data Element: Date of onset
  * AU PS Document Section: History of pregnancy
  * IPS Profile(s): -
  * FHIR Path: -
  * Comment: This AUCDI data group is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Certainty
  * AUCDI Data Element: -
  * AU PS Document Section: -
* AUCDI Data Group: Date of assertion
  * AUCDI Data Element: -
  * AU PS Document Section: -
* AUCDI Data Group: Medication use statement
  * AUCDI Data Element: Medication name
  * AU PS Document Section: Medication Summary
  * IPS Profile(s): [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)|[AU PS Medication](StructureDefinition-au-ps-medication.md)
  * FHIR Path: `MedicationStatement.medication[x] | Medication.code`
  * Comment: See the[Medicine Information](https://build.fhir.org/ig/hl7au/au-fhir-core/medicine-information.html)guidance page in AU Core.
* AUCDI Data Group: Clinical indication
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)
  * AU PS Document Section: `MedicationStatement.reasonCode | MedicationStatement.reasonReference`
* AUCDI Data Group: Strength
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)|[AU PS Medication](StructureDefinition-au-ps-medication.md)
  * AU PS Document Section: `MedicationStatement.medication[x] | Medication.code | Medication.ingredient`
* AUCDI Data Group: Form
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)|[AU PS Medication](StructureDefinition-au-ps-medication.md)
  * AU PS Document Section: `MedicationStatement.medication[x] | Medication.form`
* AUCDI Data Group: Dose amount
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)
  * AU PS Document Section: `MedicationStatement.dosage.doseAndRate`
* AUCDI Data Group: Route of administration
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)
  * AU PS Document Section: `MedicationStatement.dosage.route`
* AUCDI Data Group: Dose timing
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)
  * AU PS Document Section: `MedicationStatement.dosage.timing`
* AUCDI Data Group: Comment
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)
  * AU PS Document Section: `MedicationStatement.note`
* AUCDI Data Group: Date of assertion
  * AUCDI Data Element: [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.md)
  * AU PS Document Section: `MedicationStatement.dateAsserted`
* AUCDI Data Group: Problem/Diagnosis summary
  * AUCDI Data Element: Problem / Diagnosis name
  * AU PS Document Section: Problems | History of Past Problems
  * IPS Profile(s): [AU PS Condition](StructureDefinition-au-ps-condition.md)
  * FHIR Path: `Condition.code`
  * Comment: 
* AUCDI Data Group: Body site
  * AUCDI Data Element: [AU PS Condition](StructureDefinition-au-ps-condition.md)
  * AU PS Document Section: `Condition.code`
  * IPS Profile(s): 
* AUCDI Data Group: Date/time of onset
  * AUCDI Data Element: [AU PS Condition](StructureDefinition-au-ps-condition.md)
  * AU PS Document Section: `Condition.onsetDateTime`
  * IPS Profile(s): 
* AUCDI Data Group: Date/time of resolution
  * AUCDI Data Element: [AU PS Condition](StructureDefinition-au-ps-condition.md)
  * AU PS Document Section: `Condition.abatementDateTime`
  * IPS Profile(s): 
* AUCDI Data Group: Status
  * AUCDI Data Element: [AU PS Condition](StructureDefinition-au-ps-condition.md)
  * AU PS Document Section: `Condition.clinicalStatus`
  * IPS Profile(s): 
* AUCDI Data Group: Comment
  * AUCDI Data Element: [AU PS Condition](StructureDefinition-au-ps-condition.md)
  * AU PS Document Section: `Condition.note`
  * IPS Profile(s): 
* AUCDI Data Group: Last updated
  * AUCDI Data Element: -
  * AU PS Document Section: -
  * IPS Profile(s): This AUCDI element is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Procedure
  * AUCDI Data Element: Procedure name
  * AU PS Document Section: History of Procedures
  * IPS Profile(s): [AU PS Procedure](StructureDefinition-au-ps-procedure.md)
  * FHIR Path: `Procedure.code`
  * Comment: 
* AUCDI Data Group: Clinical indication
  * AUCDI Data Element: [AU PS Procedure](StructureDefinition-au-ps-procedure.md)
  * AU PS Document Section: `Procedure.reasonCode | Procedure.reasonReference[x]`
  * IPS Profile(s): 
* AUCDI Data Group: Body site/laterality
  * AUCDI Data Element: [AU PS Procedure](StructureDefinition-au-ps-procedure.md)
  * AU PS Document Section: `Procedure.code`
  * IPS Profile(s): 
* AUCDI Data Group: Date/time performed
  * AUCDI Data Element: [AU PS Procedure](StructureDefinition-au-ps-procedure.md)
  * AU PS Document Section: `Procedure.performed[x] | Procedure.performedDateTime`
  * IPS Profile(s): 
* AUCDI Data Group: Comment
  * AUCDI Data Element: [AU PS Procedure](StructureDefinition-au-ps-procedure.md)
  * AU PS Document Section: `Procedure.note`
  * IPS Profile(s): 
* AUCDI Data Group: Sex and gender summary
  * AUCDI Data Element: Sex assigned at birth
  * AU PS Document Section: N/A
  * IPS Profile(s): [AU PS Patient](StructureDefinition-au-ps-patient.md)
  * FHIR Path: `Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-recordedSexOrGender')`
  * Comment: The[Person Recorded Sex or Gender extension](http://hl7.org/fhir/StructureDefinition/individual-recordedSexOrGender)is profiled by[AU Core Sex Assigned At Birth (RSG)](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-rsg-sexassignedab.html)to represent the concept of Sex assigned at birth.
* AUCDI Data Group: Gender identity
  * AUCDI Data Element: [AU PS Patient](StructureDefinition-au-ps-patient.md)
  * AU PS Document Section: `Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-genderIdentity')`
  * IPS Profile(s): 
* AUCDI Data Group: Pronoun/s
  * AUCDI Data Element: [AU PS Patient](StructureDefinition-au-ps-patient.md)
  * AU PS Document Section: `Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-pronouns')`
  * IPS Profile(s): 
* AUCDI Data Group: Last updated
  * AUCDI Data Element: -
  * AU PS Document Section: -
  * IPS Profile(s): This AUCDI element is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Vaccination
  * AUCDI Data Element: Vaccine name
  * AU PS Document Section: Immunizations
  * IPS Profile(s): [AU PS Immunization](StructureDefinition-au-ps-immunization.md)
  * FHIR Path: `Immunization.vaccineCode`
  * Comment: 
* AUCDI Data Group: Sequence
  * AUCDI Data Element: [AU PS Immunization](StructureDefinition-au-ps-immunization.md)
  * AU PS Document Section: `Immunization.protocolApplied.doseNumber[x]`
  * IPS Profile(s): 
* AUCDI Data Group: Date of administration
  * AUCDI Data Element: [AU PS Immunization](StructureDefinition-au-ps-immunization.md)
  * AU PS Document Section: `Immunization.occurrenceDateTime`
  * IPS Profile(s): 
* AUCDI Data Group: Comment
  * AUCDI Data Element: [AU PS Immunization](StructureDefinition-au-ps-immunization.md)
  * AU PS Document Section: `Immunization.note`
  * IPS Profile(s): 
* AUCDI Data Group: Estimated Date of Delivery (EDD) summary
  * AUCDI Data Element: EDD by menstrual cycle
  * AU PS Document Section: History of pregnancy
  * IPS Profile(s): [Observation Pregnancy - Expected Delivery Date (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-pregnancy-edd-uv-ips.html)
  * FHIR Path: `Observation.valueDateTime`
  * Comment: This data group maps to an IPS profile; This AUCDI data group is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Date of ultrasound
  * AUCDI Data Element: [Observation Pregnancy - Expected Delivery Date (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-pregnancy-edd-uv-ips.html)
  * AU PS Document Section: `Observation.effectiveDateTime`
  * IPS Profile(s): AUCDI elements Date of ultrasound and Estimated date of delivery by ultrasound would be grouped together in the same Observation, separate to Estimated data of delivery by menstrual cycle.
* AUCDI Data Group: EDD by ultrasound
  * AUCDI Data Element: [Observation Pregnancy - Expected Delivery Date (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-pregnancy-edd-uv-ips.html)
  * AU PS Document Section: `Observation.valueDateTime`
* AUCDI Data Group: Last updated
  * AUCDI Data Element: -
  * AU PS Document Section: -
  * IPS Profile(s): This AUCDI element is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Gestation by ultrasound
  * AUCDI Data Element: -
  * AU PS Document Section: -
  * IPS Profile(s): This AUCDI element is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Pregnancy assertion
  * AUCDI Data Element: Pregnancy assertion
  * AU PS Document Section: History of pregnancy
  * IPS Profile(s): [Observation Pregnancy - Status (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-pregnancy-status-uv-ips.html)
  * FHIR Path: `Observation.valueCodeableConcept`
  * Comment: This data group maps to an IPS profile; This AUCDI data group is a[Future Candidate Requirement Under Consideration](future.md#future-candidate-requirements-under-consideration).
* AUCDI Data Group: Justification
  * AUCDI Data Element: [Observation Pregnancy - Status (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-pregnancy-status-uv-ips.html)
  * AU PS Document Section: `Observation.note`
* AUCDI Data Group: Date of assertion
  * AUCDI Data Element: [Observation Pregnancy - Status (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-pregnancy-status-uv-ips.html)
  * AU PS Document Section: `Observation.effectiveDateTime`

