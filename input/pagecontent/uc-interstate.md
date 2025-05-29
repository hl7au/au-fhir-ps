This use case describes an example scenario where, during a general practitioner (GP) consultation with a new patient who resides in a different state and has a usual GP, the GP retrieves an up-to-date patient summary from the patient's usual GP. 

### Use Case Description

Jeramy Ezra Banks is a 73-year-old male who lives in New South Wales, Australia. Jeramy has chronic heart disease which was diagnosed 5 years ago and Jeramy's usual GP is Dr Abe Lowe. Comfortable with basic technology, Jeramy uses a smartphone app to manage his healthcare records.

Jeramy travels interstate to Queensland for a holiday to visit his daughter. Prior to travelling, Jeramy checks that his patient summary has been updated by his usual GP (Dr Abe Lowe) following a recent admission to hospital.

During the trip Jeramy begins feeling unwell, he is gasping for breath and feels stiff after driving. Jeramy books an appointment with a local Queensland GP (Dr Wyatt Samuels).

Jeramy attends the appointment with the local Queensland GP (Dr Wyatt Samuels). During the appointment, Jeramy alerts the attending GP (Dr Wyatt Samuels) that a patient summary from his usual GP is available. Jeramy provides access to his patient summary to the attending GP (Dr Wyatt Samuels). 

The attending GP's (Dr Wyatt Samuels) clinical system initiates a request to retrieve Jeramy’s most recent patient summary from the clinical system of the usual GP (Dr Abe Lowe) to ensure safe and informed care.

The attending GP (Dr Wyatt Samuels) uses the patient summary to support care decisions during the consultation.

 <div> 
    <img src="uc-interstate-cj.png" alt="Interstate GP Visit consumer journey" style="width:80%"/>
  </div>
*Figure 1: Interstate GP Visit consumer journey*
<br/>

This use case demonstrates use of patient summary during step 5. Patient Summary Retrieval of the [Interstate GP Visit consumer journey](https://sparked.csiro.au/index.php/sparked-products-resources/au-patient-summary-consumer-journeys/).

<div class="stu-note" markdown="1">

#### Use Case Decisions to be confirmed for the patient summary from Usual GP
The following decisions are to be confirmed:
1. is it accessed by a QR code and/or link
1. is electronic signature present yes/no

</div>

### Actors

#### People
1. Attending GP (Dr Wyatt Samuels)
1. Patient (Jeramy)

#### Systems
1. Attending GP's Clinical Information System (CIS)
1. Usual GP's Clinical Information System

### Precondition(s)
1. Jeramy has provided consent for his health information to be shared between healthcare providers.
1. Jeramy is registered with a usual GP whose system maintains a current patient summary.
1. The attending GP system is connected to a network that allows secure record exchange.

### Postcondition(s)
1. The attending GP has accessed and reviewed Jeramy’s patient summary.
1. Any updates resulting from the consultation may be recorded in the attending GP’s system 
1. Resulting updates may be communicated back to the usual GP and patient.

### Flow
1. Jeramy presents at a general practice that is not his usual clinic.
1. The attending GP verifies Jeramy’s identity and obtains consent to access external records.
1. The attending GP system initiates a query to locate Jeramy’s usual GP.
1. The system securely requests Jeramy’s latest patient summary from the usual GP system (directly or via an exchange).
1. The usual GP system authenticates the request and returns the patient summary.
1. The attending GP reviews the summary, which may include medications, problems, allergies, immunisations, observations, and recent care events.
1. The information supports clinical decision-making during the consultation.

INSERT SEQUENCE DIAGRAM
*Figure 2: Sequence Diagram TBD*
<br/>

### Examples

The following example demonstrates technical and clinical use case aspects, conforming to the AU Patient Summary requirements. Data within this example, e.g. medications, is provided by the [Sparked Patient Summary Clinical Focus Group](https://sparked.csiro.au/index.php/design-groups/):
* Patient Summary from Usual GP CIS: [Jeramy's Patient Summary as of 27 May 2025 (Bundle)](Bundle-aups-gpvisit-retrieval.html)

<div class="stu-note" markdown="1">

</div>


