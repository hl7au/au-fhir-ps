[Section empty reason](Bundle-aups-section-emptyreason.html)

Shows an example of a software-assembled patient summary that demonstrates the system has no information for the sections: problems, allergies, medications, immunisations. Example for the *AU Patient Summary Bundle* and *AU Patient Summary Composition* profile. Patient: Ronny Lawrence Irvine.

**Document and Participants**
Item|Details
---|---
Bundle | type=document, language en-AU, 2025-02-05T19:33:11.0607701+10:00
Composition | Status final; LOINC 60591-5 (Patient summary Document); title International Patient Summary; event care provision, end 2025-01-08; date 2025-02-03
Patient | Ronny Lawrence Irvine; male; birthDate unknown (data-absent-reason); DVA Number QX827261; Indigenous status: Torres Strait Islander but not Aboriginal origin; address Belmore River NSW 2440
Author | RelatedPerson - Mr. Sonny Irvine (relationship: son)
Custodian | Douglas Radiology (Organization)
{: .grid}

**Sections**
Section title|LOINC code|Number of entries|Entry type
---|---|---|---
Allergies and Intolerances | LOINC 48765-2 | 0 | emptyReason
Problem List | LOINC 11450-4 | 0 | emptyReason
Medication Summary | LOINC 10160-0 | 0 | emptyReason
Immunizations | LOINC 11369-6 | 0 | emptyReason
{: .grid}

**Entries**
Item|Resource type|Summary|Dates|In section
---|---|---|---|---
1 | - | No clinical entries — all sections use emptyReason=unavailable | - | -
{: .grid}

**Profiles Applied**
Resource type|Profile|
---|---
Bundle | [AU PS Bundle](StructureDefinition-au-ps-bundle.html)
Composition | [AU PS Composition](StructureDefinition-au-ps-composition.html)
Organization | [AU PS Organization](StructureDefinition-au-ps-organization.html)
Patient | [AU PS Patient](StructureDefinition-au-ps-patient.html)
RelatedPerson | [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html)
{: .grid}
