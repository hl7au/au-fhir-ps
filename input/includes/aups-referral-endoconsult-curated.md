[Patient Summary for Joyce Johnson as of 28 OCT 2024 (with electronic signature)](Bundle-aups-referral-endoconsult-curated.html)

 Shows an example of a patient summary containing the medical history and current medications at the time of referral that was authored by the GP through curation of a generated view of the data within their clinical information system, and was attested at the time of creation of the patient summary and signed electronically. 

**Document and Participants**
Item|Details
---|---
Bundle | type=document, language en-AU, timestamp 2024-10-28T11:57:11.269+11:00
Composition | Status final; LOINC 60591-5 (Patient summary Document); title Patient Summary for Joyce Johnson as of 27 May 2025; date 2024-10-28T11:57:10.868+11:00
Patient | Joyce JOHNSON; Medicare Provider Number present
Author | PractitionerRole for Ginger BURROWS (Practitioner) and Bungabbee Medical Clinic (Organization)
Custodian | Windsor Medical Clinic (Organization)
{: .grid}

TBD: Signature


**Sections and entries**:
- **Allergies and Intolerances** (LOINC 48765-2):
  - 1 AllergyIntolerance entry
  - indicates the patient has No known allergy (represented by an AllergyIntolerance resource with SNOMED CT code 716186003 /|No known allergy/|).
- **Medication Summary** (LOINC 10160-0):
  - 4 MedicationStatement entries
  - all active medications, each with a start date and dateAsserted. 
  - all include contained Medication resources
- **Problem list** (LOINC 11450-4):
  - 2 Condition entries representing current conditions/problems
- **History of Immunizations** (LOINC 11369-6): 
  - 4 Immunization entries
  - all immunizations are completed with recorded occurrence dates.
  - vaccines include combination Diphtheria/tetanus/pertussis, two Influenza vaccine entries and COVID-19 vaccine (Moderna “mRNA-1273”, with manufacturer and lot number documented in those entries).
  - one influenza immunization entry includes a note about a prior reaction. Several entries carry a vaccine serial number extension and lot number. 
- **Pregnancy Information** (LOINC 10162-6):
  - 1 Observation entry
  - A pregnancy status observation (final) with the date pregnancy confirmed.
  - This observation includes a linked member Observation for the Estimated Date of Delivery (EDD)
- **Social History** (LOINC 29762-2):
  - 1 Observation entry
  - a smoking status observation (final) with 
  - it records the patient’s smoking status as "Lifetime non-smoker"

**Sections**
Section title|LOINC code|Number of entries|Entry type
---|---|---|---
Allergies and Intolerances | LOINC 48765-2 | 1 | AllergyIntolerance
Medication Summary | LOINC 10160-0 | 4 | MedicationStatement
Problems list | LOINC 11450-4 | 2 | Condition
History of Immunizations | LOINC 11369-6 | 4 | Immunization
Pregnancy Information | LOINC 10162-6 | 1 | Observation
Social History | LOINC 29762-2 | 1 | Observation
{: .grid}

**Entries** - TBD
Item|Resource type|Summary|Dates|In section
---|---|---|---|---
1 | AllergyIntolerance | TBD | TBD | Allergies/Adverse reactions

**Profiles applied**
Resource type|Profile
---|---
AllergyIntolerance | [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)
Bundle | [AU PS Bundle](StructureDefinition-au-ps-bundle.html)
Composition | [AU PS Composition](StructureDefinition-au-ps-composition.html)
Condition | [AU PS Condition](StructureDefinition-au-ps-condition.html)
Immunization| [AU PS Immunization](StructureDefinition-au-ps-immunization.html)
Medication | [AU PS Medication](StructureDefinition-au-ps-medication.html)
MedicationStatement | [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)
Observation | [AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.html)
Observation | [Observation Pregnancy - Expected Delivery Date (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-edd-uv-ips.html)
Observation | [Observation Pregnancy - Status (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-status-uv-ips.html)
Organization | [AU PS Organization](StructureDefinition-au-ps-organization.html)
Patient | [AU PA Patient](StructureDefinition-au-ps-patient.html)
Practitioner | [AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)
PractitionerRole | [AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.html)
