[Patient Summary for Joyce Johnson as of 28 OCT 2024 (with electronic signature)](Bundle-aups-referral-endoconsult-curated.html)

**Bundle overview**
- **Example id** aups-referral-endoconsult-curated
- **Bundle type**: document
- **Timestamp**: 2024-10-28T11:57:11.269+11:00
- Conforms to: AU PS Bundle profile
This Bundle represents a patient summary containing the medical history and current medications at the time of referral that was authored by the GP through curation of a generated view of the data within their clinical information system, and was attested at the time of creation of the patient summary. [Referral to Specialist and Allied Health use case](uc-referral.html) example.

**Composition & participants** 
- **Composition**: Patient Summary for Joyce Johnson as of 28 OCT 2024
- **Status**: final
- **Date**: 2024-10-28T11:57:10.868+11:00.
- **Subject**: Patient Joyce JOHNSON (includes IHI, Medicare number, and demographics (DOB 1952-09-30, female, address in VIC)).
- **Author**: PractitionerRole (General Practitioner, includes Medicare Provider Number, and references a Practitioner entry for Ginger BURROWS and an Organization entry for Bungabbee Medical Clinic). 
- **Attester**: PractitionerRole (General Practitioner). Same as the document author. 
- **Custodian**: Organization (Windsor Medical Clinic; includes HPI-O, ABN and contact details).

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

**Referenced resources**

The bundle includes references to the following resource types:
- Composition, Patient, Organization, PractitionerRole, Practitioner
- AllergyIntolerance, MedicationStatement, Medication, Condition, Immunization, Observation

**Profiles applied**

A full list of profiles:
- [AU PS Bundle](StructureDefinition-au-ps-bundle.html)
- [AU PS Composition](StructureDefinition-au-ps-composition.html)
- [AU PA Patient](StructureDefinition-au-ps-patient.html)
- [AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)
- [AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.html)
- [AU PS Organization](StructureDefinition-au-ps-organization.html)
- [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)
- [AU PS Medication](StructureDefinition-au-ps-medication.html)
- [AU PS Condition](StructureDefinition-au-ps-condition.html)
- [AU PS Immunization](StructureDefinition-au-ps-immunization.html)
- [AU PS Smoking Status](StructureDefinition-au-ps-smokingstatus.html)
- [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)
- [Observation Pregnancy - Expected Delivery Date (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-edd-uv-ips.html)
- [Observation Pregnancy - Status (IPS)](https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-status-uv-ips.html)

