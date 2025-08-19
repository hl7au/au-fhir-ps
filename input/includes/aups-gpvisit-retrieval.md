[Jeramy's Patient Summary as of 27 May 2025 (Bundle)](Bundle-aups-gpvisit-retrieval.html)

[Interstate GP use case](uc-interstate.html) example. Shows an example of a patient summary authored by the patient's usual GP that was updated after a recent admission to hospital. Example for the *AU Patient Summary Bundle* and *AU Patient Summary Composition* profile. Patient: Jeramy Ezra Banks.

**Document and Participants**
Item|Details
---|---
Bundle | type=document, language en-AU, timestamp 2025-05-27T11:57:37.051+11:00
Composition | Status final; LOINC 60591-5 (Patient summary Document); title Patient Summary for Joyce Johnson as of 07 NOV 2024; date 2025-05-27T11:57:36+11:00
Patient | Jeramy Ezra BANKS; IHI present; gender identity/pronouns extensions
Author | Practitioner Dr. Abe LOWE
Custodian | Mossy Point Medical Centre (Organization)
{: .grid}

**Sections**
Section title|LOINC code|Number of entries|Entry type
---|---|---|---
Active Problems | LOINC 11450-4 | 1 | Condition
Allergies/Adverse reactions | LOINC 48765-2 | 1 | AllergyIntolerance
Current Medications | LOINC 10160-0 | 7 | MedicationRequest
Current Medical Information | LOINC 11450-4 | 5 | Condition
Vaccination/Immunisation History | LOINC 11369-6 | 3 | Immunization
Past Medical History (Procedures) | LOINC 47519-4 | 2 | Procedure
Result History | LOINC 30954-2 | 12 | Observation
{: .grid}

**Entries**
Item|Resource type|Summary|Dates|In section
---|---|---|---|---
1 | AllergyIntolerance | No known allergy| | Allergies/Adverse reactions
2 | Condition|Hypercholesterolaemia; active; confirmed | Last updated: 2025-05-25 11:17:03+1100 | Current Medical Information
3 | Condition | Type 2 diabetes mellitus; active; confirmed|Last updated: 2025-05-25 11:17:03+1100 | Current Medical Information
4 | Condition | Hypertension; active; confirmed|Last updated: 2025-05-25 11:17:03+1100 | Current Medical Information
5 | Condition | Gout, Left great toe; active; confirmed; body site Left great toe; has a note | Last updated: 2025-05-25 11:17:03+1100 | Current Medical Information
6 | Condition | COPD; active; confirmed| Last updated: 2025-05-25 11:17:03+1100 | Current Medical Information
7 | Immunization | M-M-R II; completed| occurence unknown (data-absent-reason); Last updated: 2025-05-25 11:39:15+1100 | Vaccination/Immunisation History
8 | Immunization | Boostrix; completed| occurence unknown (data-absent-reason); Last updated: 2025-05-25 11:39:15+1100 | Vaccination/Immunisation History
9 | Immunization | AstraZeneca Vaxzevria; completed | occurence unknown (data-absent-reason); Last updated: 2025-05-25 11:39:15+1100 | Vaccination/Immunisation History
10 | Procedure | Angiogram; completed; encounter reference | Last updated: 2025-05-27 11:39:15+1100 | Past Medical History (Procedures)
11 | Procedure | Chest x-ray; completed | Last updated: 2025-05-27 11:39:15+1100 | Past Medical History (Procedures)
12 | Observation | Triglyceride; performer unknown (data-absent-reason); 1.7 mmol/L|2025-03-17 | Last updated: 2025-05-27 11:39:15+1100 | Result History
13 | Observation | HDL; performer unknown (data-absent-reason); 1.55 mmol/L | 2025-03-17; Last updated: 2025-05-27 11:39:15+1100 | Result History
14 | Observation | LDL; performer unknown (data-absent-reason); 3.10 mmol/L | 2025-03-17; Last updated: 2025-05-27 11:39:15+1100 | Result History
15 | Observation | Total Cholesterol; performer unknown (data-absent-reason); 5.4 mmol/L | 2025-03-17; Last updated: 2025-05-27 11:39:15+1100 | Result History
16 | Observation | Total Cholesterol; performer unknown (data-absent-reason); 5.7 mmol/L | 2024-12-17; Last updated: 2025-01-27 11:39:15+1100 | Result History
17 | Observation | HDL; performer unknown (data-absent-reason); 1.42 mmol/L | 2024-12-17; Last updated: 2025-01-27 11:39:15+1100 | Result History
18 | Observation | LDL; performer unknown (data-absent-reason); 3.36 mmol/L | 2024-12-17; Last updated: 2025-01-27 11:39:15+1100 | Result History
19 | Observation | Triglyceride; performer unknown (data-absent-reason); 1.8 mmol/L | 2024-12-17; Last updated: 2025-01-27 11:39:15+1100 | Result History
20 | Observation | Total Cholesterolriglyceride; performer unknown (data-absent-reason); 6.0 mmol/L | 2024-09-17; Last updated: 2024-10-27 11:39:15+1100 | Result History
21 | Observation | HDL; performer unknown (data-absent-reason); 1.29 mmol/L | 2024-09-17; Last updated: 2024-10-27 11:39:15+1100 | Result History
22 | Observation | LDL; performer unknown (data-absent-reason); 3.62 mmol/L | 2024-09-17; Last updated: 2024-10-27 11:39:15+1100 | Result History
23 | Observation | Triglyceride; performer unknown (data-absent-reason); 1.9 mmol/L | 2024-09-17; Last updated: 2024-10-27 11:39:15+1100 | Result History
24 | MedicationRequest | Ventolin; 2 puffs, 4 times per day, and as needed; active; order; encounter reference; requester Abe LOWE (Practitioner); reasonCode COPD | authoredOn unknown (data-absent-reason); Last updated: 2025-05-25 11:17:03+1100 | Current Medications
25 | MedicationRequest | Zyloprim 300 mg; once daily, Oral route; active; order; encounter reference; requester Abe LOWE (Practitioner); reasonCode Gout | authoredOn unknown (data-absent-reason); Last updated: 2025-05-25 11:17:03+1100 | Current Medications
26| MedicationRequest | Spiriva; once daily; active; order; encounter reference; requester Abe LOWE (Practitioner); reasonCode COPD | authoredOn unknown (data-absent-reason); Last updated: 2025-05-25T11:17:03.285+11:00 | Current Medications
27 | MedicationRequest | Rosuvastatin 40mg &amp; ezetrol 10mg; once daily; active; order; encounter reference; requester Abe LOWE (Practitioner); reasonCode Hypercholesterolaemia | authoredOn unknown (data-absent-reason); Last updated: 2025-05-25T11:17:03.285+11:00 | Current Medications
28 | MedicationRequest | Metformin 500 mg; twice daily; active; order; encounter reference; requester Abe LOWE (Practitioner); reasonCode Type 2 diabetes mellitus | authoredOn unknown (data-absent-reason); Last updated: 2025-05-25T11:17:03.285+11:00 | Current Medications
29 | MedicationRequest | Aspirin 100 mg; once daily; active; order; requester Abe LOWE (Practitioner); reasonCode Type Cardiovascular disease | authoredOn unknown (data-absent-reason); Last updated: 2025-05-25T11:17:03.285+11:00 | Current Medications
30 | MedicationRequest | Telmisartan 80 mg; once daily; active; order; requester Abe LOWE (Practitioner); reasonCode Type Hypertension | authoredOn unknown (data-absent-reason); Last updated: 2025-05-25T11:17:03.285+11:00 | Current Medications
{: .grid}

TODO
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


**Profiles Applied**
Resource type|Profile|
---|---
AllergyIntolerance | [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)
Bundle | [AU PS Bundle](StructureDefinition-au-ps-bundle.html)
Composition | [AU PS Composition](StructureDefinition-au-ps-composition.html)
Condition | [AU PS Condition](StructureDefinition-au-ps-condition.html)
Encounter | [AU PS Encounter](StructureDefinition-au-ps-encounter.html)
Immunization | [AU PS Immunization](StructureDefinition-au-ps-immunization.html)
Location | [AU Core Location](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-location.html)
MedicationRequest | [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.html)
Observation | [AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.html)
Organization | [AU PS Organization](StructureDefinition-au-ps-organization.html)
Patient | [AU PS Patient](StructureDefinition-au-ps-patient.html)
Practitioner | [AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)
Procedure | [AU PS Procedure](StructureDefinition-au-ps-procedure.html)
{: .grid}

