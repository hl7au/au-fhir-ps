[Bundle - Basic summary](Bundle-aups-basicsummary.html)

Shows an example of a provider curated patient summary that demonstrates no known problems or disabilities, current allergies and intolerances, and current medication use. Example for the *AU Patient Summary Bundle* and *AU Patient Summary Composition* profile. Patient: Mia Leanne Banks.


Key characteristics
- Authored by a General Practitioner using a PractitionerRole referencing
  - practitioner: Dr. Bob Bobrester
  - organization: Bobrester Medical Center
- Custodian 
  - the document custodian is the Organization Bobrester Medical Center
- Sections included
  - Active Problems (LOINC 11450-4)
    - includes a reference to a Condition indicating 160245001 | No current problems or disability
    - recorded date
  - Active Allergies or Intolerances (LOINC 48765-2)
    - ad6fb7b7-c76f-441e-88a5-9051e795db26 AllergyIntolerance, active, confirmed, intolerance to lactose, onset datetime, recordered date, multiple manifestation
    - 06ba95f5-345b-412d-aa66-99e354470015
    - d24db2d5-3400-4158-892c-d018acdeba09
  - Current Medicines (LOINC 10160-0)
    - includes a reference to a MedicationStatement Bisoprolol fumarate
    - The MedicationStatement includes a contained Medication resource

**Bundle overview**
- **Example id** aups-gpvisit-retrieval
- **Bundle type**: document
- **Timestamp**: 2025-02-05T19:33:11.0607701+10:00
- **Conforms to**: AU PS Bundle
- The Bundle provider curated patient summary that demonstrates no known problems or disabilities, current allergies and intolerances, and current medication use.

**Composition & participants** 
- **Title**: International Patient Summary
- **Date**: 2025-02-03
- **Subject**: Mia Leanne Banks(includes IHI, demographics, pronouns and gender identity)
- **Author**: PractitionerRole (General Practitioner, references Dr. Bob Bobrester and organization Bobrester Medical Center).
- **Custodian**: Organization Bobrester Medical Center

**Sections and entries**
- **Active Problems** (LOINC 11450-4 – Problem list, Reported)
  - 1 Condition entry
  - Indicates no current problem or disability
  - **Active Allergies or Intolerances** (LOINC 48765-2 – Allergies and adverse reactions Document)
  - 3 AllergyIntolerance entries
  - all entres include onset and recorded date, manifestation and reaction severity
- **Current Medicines** (LOINC 10160-0 – History of Medication use)
  - 1 x MedicationStatement
  - Include dosage instructions and a contained Medication resource


**Referenced resources**

The Bundle includes references to the following resource types:
- Composition, Patient, , PractitionerRole, Practitioner, Organization
- AllergyIntolerance, MedicationStatement, Condition, Medication 

**Profiles applied**

Every resource in the Bundle declares conformance to the AU PS profiles for that resource type, e.g. Bundle declares conformance to [AU PS Bundle](StructureDefinition-au-ps-bundle.html) via meta.profile.
Each entries meta also show versionId and lastUpdated timestamp. A full list of profiles:
- [AU PS Bundle](StructureDefinition-au-ps-bundle.html)
- [AU PS Composition](StructureDefinition-au-ps-composition.html)
- [AU PA Patient](StructureDefinition-au-ps-patient.html)
- [AU PS Practitioner](StructureDefinition-au-ps-practitioner.html)
- [AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.html)
- [AU PS Organization](StructureDefinition-au-ps-organization.html)
- [AU PS MedicationStatement](StructureDefinition-au-ps-medicationstatement.html)
- [AU PS Medication](StructureDefinition-au-ps-medication.html)
- [AU PS Condition](StructureDefinition-au-ps-condition.html)
- [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html)
