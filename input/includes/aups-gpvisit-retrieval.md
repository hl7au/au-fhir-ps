[Jeramy's Patient Summary as of 27 May 2025 (Bundle)](Bundle-aups-gpvisit-retrieval.html)

[Interstate GP use case](uc-interstate.html) example. Shows an example of a patient summary authored by the patient's usual GP that was updated after a recent admission to hospital. Example for the *AU Patient Summary Bundle* and *AU Patient Summary Composition* profile. Patient: Jeramy Ezra Banks.

**Bundle overview**
- **Example id** aups-gpvisit-retrieval
- **Bundle type**: document
- **Timestamp**: 2025-05-27T11:57:37.051+11:00
- **Conforms to**: AU PS Bundle
- The Bundle conforms to the AU PS Bundle profile and contains a Composition plus all referenced resources (entries) that make up the patient summary. 

**Composition & participants** 
- **Title**: Jeramy's Patient Summary
- **Date**: 2025-05-27T11:57:36+11:00.
- **Subject**: Patient Jeramy Ezra BANKS. The Patient entry includes identifiers (e.g. IHI, Medicare number) and demographics (DOB 1971-05-14, male, address in NSW) 
- **Author**: Practitioner Dr. Dr. Abe LOWE (Jeramy's GP; includes HPI-I, prescriber number, and contact details).
- **Custodian**: Organization Mossy Point Medical Centre (includes HPI-O, ABN, and contact details).

**Sections and entries**
- **Allergies/Adverse reactions** (LOINC 48765-2 – Allergies and adverse reactions Document)
  - 1 AllergyIntolerance entry
  - Indicates No known allergy (represented by an AllergyIntolerance resource with SNOMED CT code 716186003 /|No known allergy/|).
- **Current Medications** (LOINC 10160-0 – History of Medication use)
  - 7 x MedicationRequest entries
  - These are the patient’s active medication orders, e.g. Metformin 500 mg (for Type 2 diabetes), Aspirin 100 mg (for cardiovascular disease), Telmisartan 80 mg (for hypertension). 
  - Each MedicationRequest is marked “active” and include dosage instructions and a clinical indication
- **Current Medical Information** (LOINC 11450-4 – Problem list, Reported)
  - 5 Condition entries capturing active problems/diagnoses, e.g. Hypertension, Type 2 diabetes mellitus, Hypercholesterolaemia, Gout (Left great toe), and COPD. 
  - Each Condition is “active” clinical status and “confirmed” verification status, categorised as problem-list items. 
  - The Gout condition entry also specifies body site and notes.
- **Vaccination/Immunisation History** (LOINC 11369-6 – History of Immunization)
  - 3 Immunization entries
  - These record past vaccines: M-M-R II (Measles-Mumps-Rubella), Boostrix (Tdap booster), and AstraZeneca Vaxzevria (COVID-19 vaccine).
  - Each Immunization entry has status="completed" and missing data for dates of vaccination.
- **Past Medical History (Procedures)** (LOINC 47519-4 – History of Procedures Document): 
  - 2 Procedure entries 
  - These are recent procedures the patient underwent: an Angiogram on 2025-05-22 (reason: recent chest pain), and a Chest X-ray on 2025-02-22.
 - Both Procedure entries have status “completed” and reference the encounter during which they occurred.
- **Result History** (LOINC 30954-2 – Relevant diagnostic tests/laboratory data):
  - 12 Observation entries representing lab results.
  - These Observations capture a lipid panel (cholesterol tests) from three different dates. For each of dates, there are four Observations: Total Cholesterol, HDL, LDL, and Triglycerides. 
  - Each Observation has status="final" and category “laboratory”, with the test coded by LOINC (e.g. LOINC 14647-2 for total cholesterol) and the result value and unit provided.
  - All Observations include missing data for performer.

**Key encounters**

- **GP Visit Encounter**
  - An ambulatory general practice visit for follow-up, which took place at the patient’s GP clinic.
  - class=AMB (ambulatory), service type "General practice service".
  - The encounter’s period ended on 2025-02-25.
  - The primary performer (Encounter.participant) is the GP author, Dr. LOWE, and the service provider is Mossy Point Medical Centre.
  - Most of the MedicationRequests are linked to this encounter (indicating they were prescribed during that GP visit). 
- **Hospital Encounter**:
  - An inpatient hospital admission related to the patient’s angiography.
  - class=IMP (inpatient hospitalization), service type "Cardiac diagnostic service".
  - It covers period from 2025-05-22 to 2025-05-23.
  - The location is Kensington Public Hospital (provided via a Location resource), and the serviceProvider is the Organization Kensington Public Hospital.
  - Referenced by angiogram Procedure entry, and one of the MedicationRequests (the rosuvastatin/ezetimibe combination for hypercholesterolemia) was also associated with this hospital encounter.

**Referenced resources**

The Bundle includes references to the following resource types:
- Composition, Patient, Practitioner, Organization
- AllergyIntolerance, MedicationRequest, Condition, Immunization, Procedure, Observation, Encounter, Location

**Profiles applied**

Every resource in the Bundle declares conformance to the AU PS profiles for that resource type, e.g. Bundle declares conformance to [AU PS Bundle](StructureDefinition-au-ps-bundle.html) via meta.profile.
Each entries meta also show versionId and lastUpdated timestamp. A full list of profiles:
- [AU PS Bundle](StructureDefinition-au-ps-bundle.html)
- [AU PS Composition](StructureDefinition-au-ps-composition.html)
- [AU PA Patient](StructureDefinition-au-ps-patient.html)
- [AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)
- [AU PS Organization](StructureDefinition-au-ps-organization.html)
- [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)
- [AU PS Condition](StructureDefinition-au-ps-condition.html)
- [AU PS Immunization](StructureDefinition-au-ps-immunization.html)
- [AU PS Procedure](StructureDefinition-au-ps-procedure.html)
- [AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)
- [AU PS Encounter](StructureDefinition/au-ps-encounter.html)
- [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)
- [AU Core Location](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-location.html)