This example use case describes a possible scenario where, during a general practitioner (GP) consultation with a new patient who resides in a different state and has a usual GP, the GP retrieves an up-to-date patient summary from the patient's usual GP. 

The example use cases in AU Patient Summary (AU PS) are provided for **illustrative purposes only** and are intended to support understanding of how patient summaries conformant to AU PS can be produced and consumed. While every effort has been made to provide useful examples, these use cases are not a normative part of the specification, nor are they fully representative of real world clinical workflows.

When reviewing clinical information such as an AU PS document, a clinician should use their clinical discretion as to the relevance of that information, as the AU PS document cannot be assumed to be complete or the most recent as it is relying on information from source systems and is not the system of record, or the system used in the creation of clinical data, rather a summary of data that can be used by a clinician as part of their clinical process to support and inform an individual's care/treatment.


### Use Case Description

Jeramy Ezra Banks, a 73-year-old man from New South Wales, has been managing chronic heart disease since his diagnosis five years ago. His regular GP, Dr Abe Lowe, oversees his ongoing care. Comfortable with basic technology, Jeramy uses a smartphone app to access and manage his health records.

Before travelling to Queensland for a holiday to visit his daughter, Jeramy confirms via the app that his patient summary has been updated by Dr Lowe following a recent hospital admission.

While on the road, Jeramy begins to feel unwell - he is gasping for breath and feels stiff after driving. He books an appointment with a local GP in Queensland, Dr Wyatt Samuels.

During the consultation, Jeramy informs Dr Samuels that his health information is available via a patient summary shared by his regular GP. Jeramy provides access using a [Smart Health Link](https://build.fhir.org/ig/HL7/smart-health-cards-and-links/) presented via his smartphone app. Dr Samuels retrieves the most recent patient summary directly from Dr Lowe’s clinical information system (CIS). The patient summary has been curated by Dr Lowe and attested at the time of update, ensuring its integrity and alignment with clinical standards. 

The summary enables Dr Samuels to quickly understand Jeramy’s condition, recent treatment, and current medications - supporting safe and informed clinical decision-making during the consultation.

<div> 
  <img src="uc-interstate-cj.png" alt="Interstate GP Visit consumer journey" style="width:80%"/>
</div>
*Figure 1: Interstate GP Visit consumer journey*
<br/>

This use case demonstrates use of patient summary during step 5. Patient Summary Retrieval of the [Interstate GP Visit consumer journey](https://sparked.csiro.au/index.php/products-resources/au-ps-consumer-journeys/).

### Actors

#### People
1. Patient - Jeramy Ezra Banks
1. Usual GP - Dr Abe Lowe
1. Attending GP - Dr Wyatt Samuels

#### Systems
1. Clinic CIS (Attending GP)
1. Patient Summary Host

### Precondition(s)
1. Jeramy has provided consent for his health information to be shared between healthcare providers.
1. Jeramy is registered with a usual GP (Dr Abe Lowe) whose CIS maintains a current patient summary.
1. Dr Lowe's system is capable of sharing patient summaries externally.
1. Dr Wyatt Samuels’ CIS is Smart Health Link capable and connected to a network that allows secure record exchange.
1. Jeramy's patient summary has been recently updated.
1. Jeramy presents at a general practice that is not his usual clinic.
1. The attending GP (Dr Wyatt Samuels) verifies Jeramy’s identity and obtains consent to access external records and a QR code from Jeramy.

### Postcondition(s)
1. Dr Wyatt Samuels has accessed and reviewed Jeramy’s patient summary.
1. Any updates resulting from the consultation may be recorded in Dr Samuels’ CIS. 
1. Resulting updates may be communicated back to Dr Lowe and Jeramy to maintain continuity of care.

### Flow
1. Dr Samuels’ CIS scans the QR code to gain access to the patient summary via the Smart Health Link.
1. The patient summary is retrieved from a Patient Summary Health system indicated by the Smart Health Link. 
1. Dr Samuels views the patient summary in the consultation.

#### Sequence Diagram
<div class="mermaid" style="padding:20px;width:800px">
---
config:
  theme: default
---
sequenceDiagram
  actor Attending GP as Attending GP
  participant Clinic CIS as Clinic CIS
  participant Patient Summary Host as Patient Summary Host
  Attending GP ->> Clinic CIS: Scan QR for Patient Summary access
  Clinic CIS ->> Patient Summary Host: Retrieve Patient Summary
  Attending GP ->> Clinic CIS: View Patient Summary
</div>
*Figure 2: Sequence diagram showing access to a patient summary via Smart Health Link*
<br/>

### Notes

The use of Smart Health Links in this scenario reflects an emerging standard for secure sharing of patient summaries. At the time of publication, the [Smart Health Link specification](https://build.fhir.org/ig/HL7/smart-health-cards-and-links/) is still evolving, and implementers should refer to the latest guidance from HL7 International and the FHIR Infrastructure Workgroup. 

### Examples

The following example demonstrates both technical and clinical aspects of the use case, conforming to the AU Patient Summary requirements. Data within this example, e.g. medications, is provided by the [Sparked Patient Summary Clinical Focus Group](https://sparked.csiro.au/index.php/design-groups/):
* Patient Summary from Usual GP CIS: [Jeramy's Patient Summary as of 27 May 2025 (Bundle)](Bundle-aups-gpvisit-retrieval.html)


