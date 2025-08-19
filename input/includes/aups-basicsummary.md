[Bundle - Basic summary](Bundle-aups-basicsummary.html)

Shows an example of a provider curated patient summary that demonstrates no known problems or disabilities, current allergies and intolerances, and current medication use. Example for the *AU Patient Summary Bundle* and *AU Patient Summary Composition* profile. Patient: Mia Leanne Banks.

**Document and Participants**
Item|Details
---|---
Bundle | type=document, language en-AU, timestamp 2025-02-05T19:33:11+10:00
Composition | Status final; LOINC 60591-5 (Patient summary Document); title International Patient Summary; date 2025-02-03
Patient | Mia Leanne Banks; IHI present; gender identity/pronouns extensions
Author | PractitionerRole for Dr Bob Bobrester
Custodian | Bobrester Medical Center (Organization)
{: .grid}

**Sections**
Section title|LOINC code|Number of entries|Entry type
---|---|---|---
Active Allergies or Intolerances | LOINC 48765-2 | 3 | AllergyIntolerance
Active Problems | LOINC 11450-4 | 1 | Condition
Current Medicines|LOINC 10160-0 | 1 | MedicationStatement, with a contained Medication resource
{: .grid}

**Entries**
Item|Resource type|Summary|Dates|In section
---|---|---|---|---
1 | AllergyIntolerance | Lactose intolerance — mild (abdominal pain/bloating/diarrhoea) | Onset 2022; Recorded 2023-03-14 | Active Allergies or Intolerances
2 | AllergyIntolerance | Gluten intolerance — mild (fatigue) | Onset 1999; Recorded 2023-01-12 | Active Allergies or Intolerances
3 | AllergyIntolerance | Chlorhexidine — mild (hives) | Onset 2023-01-12; Recorded 2023-09-09 | Active Active Allergies or Intolerances
4 | Condition | No current problems or disability | Recorded 2024-12-21 | Active Problems
5 | MedicationStatement | Bisoprolol 2.5 mg tablet - ½ tablet in the morning | Asserted 2025-01-05 | Current Medicines


{: .grid}

**Profiles Applied**
Resource type|Profile|
---|---
AllergyIntolerance | [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)
Bundle | [AU PS Bundle](StructureDefinition-au-ps-bundle.html)
Composition | [AU PS Composition](StructureDefinition-au-ps-composition.html)
Condition | [AU PS Condition](StructureDefinition-au-ps-condition.html)
Medication | [AU PS Medication](StructureDefinition-au-ps-medication.html)
MedicationStatement | [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)
Organization | [AU PS Organization](StructureDefinition-au-ps-organization.html)
Patient | [AU PS Patient](StructureDefinition-au-ps-patient.html)
Practitioner | [AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)
PractitionerRole | [AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.html)
{: .grid}