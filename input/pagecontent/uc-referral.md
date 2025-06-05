This use case demonstrates an example scenario where, during a specialist consultation, the specialist accesses the patient summary created at the time of the referral and confirms the latest patient summary available for a patient.

### Use Case Description

Joyce Johnson, a 39-year-old woman from New South Wales, is pregnant and has recently been diagnosed with gestational diabetes. To provide Joyce with more comprehensive support, her regular general practitioner (GP), Dr Ginger Burrows, refers Joyce to both an endocrinologist and a dietitian.

As part of the referral, Dr Burrows includes an embedded patient summary that captures Joyce’s medical history and current medications at the time. This embedded summary is curated from Dr Burrow's clinical information system and attested at the time of creation, ensuring its integrity and alignment with clinical standards.

The referral is received and triaged by both the endocrinologist and the dietitian. When Joyce later attends her appointment with the endocrinologist, the clinical information system alerts the provider that a more recent patient summary is available from an external source, in this case from the referring GP's clinical information system.

The endocrinologist accesses and compares both the original embedded summary and the newer version to verify the currency and accuracy of Joyce’s clinical information. The more recent patient summary has been generated at the time of request for access by Dr Burrow's clinical information system and digitally signed to ensure integrity in transit.

Based on updated data - particularly around Joyce's medication regimen - the endocrinologist adjusts Joyce’s insulin dosage and documents the decision.

An updated treatment plan is then shared with Joyce and Dr Burrows to maintain continuity of care across providers.

 <div> 
    <img src="uc-referral-cj.png" alt="Referral to Specialist and Allied Health consumer journey" style="width:65%"/>
  </div>
*Figure 1: Referral to Specialist and Allied Health consumer journey*
<br/>


This use case demonstrates use of patient summary during step 4. Endocrinologist Consultation of the [Referral to Specialist and Allied Health consumer journey](https://sparked.csiro.au/index.php/sparked-products-resources/au-patient-summary-consumer-journeys/).

### Actors

#### People
1. Endocrinologist
2. Patient (Joyce Johnson)
3. Referring GP (Dr. Ginger Burrows)

#### Systems
1. GP Clinical Information System (CIS)
2. Endocrinologist CIS
3. External system to provide the most recent patient summary

### Precondition(s)
1. The referral from the GP includes a patient summary at the time of referral.
2. A more recent patient summary is available from an external source. This may be the original GP, or may be a national health record system.
3. The Endocrinologist’s system can access both documents.

### Postcondition(s)
1. The Endocrinologist uses the information to guide clinical decisions.
2. Treatment changes are recorded in the endocrinologist's system and are communicated back to the GP and patient.

### Flow
1. Joyce attends her scheduled consultation with the Endocrinologist.
2. The Endocrinologist opens the referral in their CIS, accesses and reviews the embedded patient summary.
3. The Endocrinologist's CIS alerts that a more recent patient summary is available from another source.
4. The Endocrinologist accesses the more recent patient summary, comparing the embedded patient summary to the more recent patient summary, and verifies consistency in medications and medical history.
5. The Endocrinologist notes updated clinical information, including changes to Joyce’s insulin regimen.
6. Based on the review and patient discussion, the Endocrinologist decides to increase Joyce’s insulin dose and documents this within their CIS.

INSERT SEQUENCE DIAGRAM
*Figure 2: Sequence Diagram TBD*
<br/>

### Examples

The following examples demonstrate technical and clinical use case aspects, conforming to the AU Patient Summary requirements. Data within these examples, e.g. medications, is provided by the [Sparked Patient Summary Clinical Focus Group](https://sparked.csiro.au/index.php/design-groups/):
1. Patient Summary Embedded in Referral: [Patient Summary for Joyce Johnson as of 28 OCT 2024 (Bundle)](Bundle-aups-referral-endoconsult-curated.html)
1. More recent Patient Summary: [Patient Summary for Joyce Johnson as of 07 NOV 2024 (Bundle)](Bundle-aups-referral-endoconsult-autogen.html)