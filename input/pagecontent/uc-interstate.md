This use case describes a scenario where, during a general practitioner (GP) consultation with a new patient who resides in a different state and has a usual GP, the GP retrieves an up-to-date patient summary from the patient's usual GP. 

This use case demonstrates use of patient summary during step 5 (Patient Summary Retrieval) of the [Interstate GP Visit consumer journey](https://sparked.csiro.au/index.php/sparked-products-resources/au-patient-summary-consumer-journeys/).

### Use Case Description

Jeramy Ezra Banks is a 73-year-old male. Jeramy is a retired schoolteacher that lives in Mossy Point, NSW, Australia. Jeramy has chronic heart disease which was diagnosed 5 years ago and Jeramy's usual GP is Dr Abe Lowe. Comfortable with basic technology, Jeramy uses a smartphone app to manage his healthcare records.

Jeramy travels interstate to Queensland for a holiday to visit his daughter. Jeramy checks that his patient summary has been updated by his usual GP (Dr Abe Lowe) following a recent admission to hospital prior to travelling.

During the trip Jeramy begins feeling unwell and books an appointment with a local Queensland GP (Dr Wyatt Samuels). Jeramy is gasping for breath and feels stiff after driving.

Jeramy attends the appointment with the local Queensland GP (Dr Wyatt Samuels). During the appointment, Jeramy alerts the attending GP (Dr Wyatt Samuels) that a patient summary is available. Jeramy provides access to his updated patient summary to the attending GP (Dr Wyatt Samuels). The attending GP's (Dr Wyatt Samuels) clinical system initiates a request to retrieve Jeramy’s most recent patient summary from the clinical system of the usual GP (Dr Abe Lowe) to ensure safe and informed care.

The attending GP (Dr Wyatt Samuels) uses the patient summary to support care decisions during the consultation.


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

