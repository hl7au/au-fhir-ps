This use case demonstrates a scenario where, during a specialist consultation, the specialist accesses the patient summary created at the time of the referral and confirms the latest patient summary available for a patient.

This use case demonstrates use of patient summary during step 5 (Endocrinologist Retrieval) of the [Referral to Specialist and Allied Health consumer journey](https://sparked.csiro.au/index.php/sparked-products-resources/au-patient-summary-consumer-journeys/).

### Use Case Description

Joyce Johnson is a 39yo female who lives in New South Wales, Australia. Joyce is currently pregnant and has been recently diagnoses with gestational diabetes. Joyce’s general practitioner (GP), Dr Ginger Burrows, has decided to refer Joyce to an Endocrinologist and a Dietitian to provide Joyce for further evaluation and support.

The referral includes an embedded patient summary containing Joyce's medical history and current medications at the time of referral. The embedded patient summary was authored by the GP (Dr. Ginger Burrows) through curation of a generated view of the data within their clinical information system, and was attested at the time of creation of the patient summary.

 Each health care provider has received and triaged the referral.

Joyce attends the consultation with the Endocrinologist. During the consultation, the Endocrinologist’s clinical system notifies them that a more recent patient summary is available from an external source, such as an updated version from the referring GP, a national health record system or another provider.

The Endocrinologist accesses and compares both patient summaries to verify the accuracy and currency of the clinical information. After reviewing the most recent data -  particularly Joyce’s current medication regimen - the Endocrinologist decides to adjust the insulin dosage and documents the decision. An updated treatment plan is shared with Joyce and the referring GP (Dr Ginger Burrows) to ensure continuity of care.

<div class="stu-note" markdown="1">

#### Use Case Decisions to be confirmed for the patient summary embedded in referral
The following decisions are to be confirmed:
1. is it accessed by a QR code and/or link

The following is to be decided:
1. what is the mechanism for embedding the patient summary
1. is electronic signature present yes/no

</div>

<div class="stu-note" markdown="1">

#### Use Case Decisions to be confirmed for more recent patient summary
The following decisions are to be confirmed:
1. Attested by a digital signature by an authoritative source - and what that means
1. how is discovery of the most recent undertaken - is this search using limited info or is this out of scope of this use case

The following is to be decided:
1. what external system to provide the most recent patient summary
1. what kind of 'device' is considered to author this
1. what data is in this 'most recent' - what's different to the patient summary at time of referral?
1. what sort of link/QR code/RESTfulAPI can be used to access the summary
1. how is currency detected? is it indicated in the payload? or is this out of scope?

</div>


### Actors

#### People
1. Endocrinologist
2. Patient (Joyce Johnson)
3. Referring GP (Dr. Ginger Burrows)

#### Systems
1. GP Clinical Information System (CIS)
2. Endocronoligst CIS
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

**[EXAMPLE 01 - PATIENT SUMMARY EMBEDDED IN REFERRAL](Bundle-aups-referral-endoconsult-01.html)**

<div class="stu-note" markdown="1">

**TODO for Example 01 - patient summary embedded in a referral**
This is a Work in Progress. To dos include:
1. use case decisions still to be made (see above) - as decisions are made they will be reflected in the example
2. More immunization history to be added. 
3. Diagnostic Results to be added. 

_Note: the example data e.g. immunisation history, meds, etc. are provided by the AU Patient Summary Clinical Focus Group._

</div>


**TBD EXAMPLE O2 - MOST RECENT PATIENT SUMMARY**


<div class="stu-note" markdown="1">

**TODO FOR Example 02 - more recent patient summary**
Pre-requisite decisions to get started are:
1. what external system to provide the most recent patient summary
1. what kind of 'device' is considered to author this
1. what data is in this 'most recent' - what's different to the patient summary at time of referral?

</div>