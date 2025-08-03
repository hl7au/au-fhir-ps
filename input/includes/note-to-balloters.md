<div class="note-to-balloters" markdown="1">

#### AU Patient Summary 0.3.0 Ballot for Comment August 2025

This Ballot for Comment is opened during this cycle to solicit feedback and approval from the wider community. Feedback provided during the balloting process will be reconciled by the [AU Core Technical Design Group](https://confluence.hl7.org/display/HAFWG/HL7+Australia+-+AU+Core+Technical+Design+Group+Home).

The ballot period is 11 August 2025 to 07 September 2025.

Information on how to provide feedback for balloters is available on this Confluence page: [Guidance: Ballot Voting](https://confluence.hl7.org/display/HA/Guidance%3A+Ballot+Voting).

**Outstanding Changes Not Applied**
- [AU PS AllergyIntolerance](StructureDefinition-au-ps-allergyintolerance.html):
  - change AllergyIntolerance.reaction.manifestation binding to an NCTS Clinical Manifestation value set [AU Base: FHIR-47076](https://jira.hl7.org/browse/FHIR-47076)
- [AU PS Medication](StructureDefinition-au-ps-medication.html):
  - Change Medication.ingredient.item[x] binding to update when the AU Base AMT Medicinal Product and Substances value set moves to be an NCTS managed value set [AU Base: FHIR-44781](https://jira.hl7.org/browse/FHIR-44781)

  **Ongoing IPS 2.0.0 Work**
  The content of this release of AU PS is based on the currently approved set of changes for IPS 2.0.0 as of 4 August 2025. Work on IPS 2.0.0 is ongoing and as such changes approved post publication of this release are expected. The CI Build for IPS pre-applies the latest proposed changes, and can be used a a reference for potential changes to AU PS that will be inherited from IPS 2.0.0. [IPS Block Vote 12](https://jira.hl7.org/issues/?jql=project%20%3D%20FHIR%20AND%20Specification%20~%20%22International%20Patient%20Summary%22%20AND%20createdDate%20%3E%202023-01-01%20AND%20cf%5B11402%5D%20%3D%20Block-Vote-12) and [IPS Block Vote 13](https://jira.hl7.org/issues/?jql=project%20%3D%20FHIR%20AND%20Specification%20~%20%22International%20Patient%20Summary%22%20AND%20createdDate%20%3E%202023-01-01%20AND%20cf%5B11402%5D%20%3D%20Block-Vote-13) can be referred to for a list of the remaining IPS 2.0.0 changes to be approved.
  
</div><!-- note-to-balloters -->