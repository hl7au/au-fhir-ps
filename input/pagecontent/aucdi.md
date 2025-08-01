[Australian Clinical Data for Interoperability (AUCDI)](https://sparked.csiro.au/index.php/sparked-products-resources/aucdi/) and AU Patient Summary (AU PS) complement each other assisting in common understanding of clinical data concepts when implemented in systems and exchanged between systems.  

AUCDI defines data groups comprising one or more data elements and references clinical terminology concepts, forming the foundation of a common language to allow systems to exchange semantically accurate data more efficiently. AUCDI defines clinical requirements for the data required to support the provision of care, exchange, aggregation for analysis, and to support clinical decision support. AUCDI may define requirements that are future focussed and as yet do not align with system implementation of the clinical concept.

AU PS is a technical specification that addresses constraints and obligations on data representation for generation, exchange, and consumption of patient summaries in the Australian healthcare context. AU PS enables system data to be mapped to an agreed FHIR format for systems in Australia.

  <div> 
    <img src="aucdi2ps.png" alt="AUCDI and AU Patient Summary Development Approach" style="width:55%"/>
  </div>
*Figure 1: AUCDI and AU PS development approach*
<br/><br/>

An interpretation of AUCDI clinical information requirements through community consensus is undertaken to define support for the exchange of clinical and administrative data within technical constraints. Note that:
* In any particular release, AU Core or AU PS may not cover all AUCDI data concepts, especially when AUCDI data concepts are not supported in existing systems.
* AU PS includes exchange for concepts that are commonly implemented in systems and not included in AUCDI e.g. `Patient.name`, `Practitioner.identifier`, `Procedure.encounter`. 
* AU PS includes exchange for clinical concepts not yet included in AUCDI, e.g. MedicationRequest, which are included through reference to IPS or AU Core.
* AU PS includes data elements not included in AUCDI that are required to make FHIR implementable e.g. `Observation.status`, `MedicationRequest.intent`, Provenance.

### AUCDI and AU PS Versions

AUCDI R2 builds upon R1, expanding on the initial “core”, introducing additional data groups to support different use cases including "Patient summary":

AUCDI Version | AU PS Version
---|---
R1| -
R2 (Patient summary)|1.0.0
{:.grid}

### AUCDI (Patient summary) Mappings Into AU PS

The table below shows the relationship between data defined in the "Patient summary" AUCDI Data Groups and Elements, AU Core profiles, and AU PS profiles.<br/>

Column attribute descriptions are as follows:
- **AUCDI Data Group**: The name of the AUCDI data group.
- **AUCDI Data Element**: The name of the AUCDI data element within an AUCDI data group.
- **AU PS Document Section**: The AU PS Document section relevant for exchange (see [Structure of the Australian Patient Summary (AU PS)](the-aups.html#structure-of-the-au-ps)).
- **AU PS Profile(s)**: The title of the AU PS profile relevant for exchange.
- **FHIR Path**: The [FHIRPath expression](https://build.fhir.org/ig/HL7/FHIRPath/) to the FHIR element relevant for exchange, i.e. the FHIR element that can be populated with data from a source system that represents the clinical concept expressed in the AUCDI data element. 
- **Comment**: Additional information about the mapping including an explanation of where an element or group is not yet mapped.

<table border="1" cellspacing="0" cellpadding="0" width="100%">
<thead>
  <tr style="background-color: #f2f2f2;">
    <th>AUCDI Data Group</th>
    <th colspan="2">AUCDI Data Element</th>
    <th>AU PS Document Section</th>
    <th>AU PS Profile(s)</th>
    <th>FHIR Path</th>
    <th>Comment</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="6">Adverse reaction risk summary</td>
    <td colspan="2">Substance name</td>
    <td rowspan="6">Allergies and Intolerances</td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td><code>AllergyIntolerance.code</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date/time of onset of first reaction</td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td>TBD</td>
    <td>There is no native FHIR element or extension available with this exact meaning. Possible options are to:
<ul><li>map to AllergyIntolerance.onsetDateTime noting that allergies and intolerances may be identified without a reaction so this may not identify a first reaction.</li>
<li>map to AllergyIntolerance.reaction.onsetDateTime and the first reaction is just understood as the earliest noting that not all reactions may be captured.</li>
<li>develop a FHIR extension to capture the date time of the first reaction - to be submitted for consideration in the FHIR Extensions Pack.</li>
</ul>&#xA;&#xA;Please provide your feedback on possible mapping options on <a href="https://confluence.hl7.org/spaces/HAFWG/pages/288069416/AUCDI+R2+in+AU+PS+R1">this page</a>.</td>
  </tr>
  <tr>
    <td colspan="2">Manifestation</td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td><code>AllergyInterolance.reaction</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Severity of reaction</td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td><code>AllergyIntolerance.reaction.severity</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td><code>AllergyIntolerance.note</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Last updated</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td rowspan="3">Last Menstrual Period (LMP) assertion</td>
    <td colspan="2">Date of onset</td>
    <td rowspan="3">History of pregnancy</td>
    <td>-</td>
    <td>-</td>
    <td rowspan="3">This AUCDI data group is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td colspan="2">Certainty</td>
    <td>-</td>
    <td>-</td>
  </tr>
  <tr>
    <td colspan="2">Date of assertion</td>
    <td>-</td>
    <td>-</td>
  </tr>
  <tr>
    <td rowspan="9">Medication use statement</td>
    <td colspan="2">Medication name</td>
    <td rowspan="9">Medication Summary</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a> | <a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
    <td><code>MedicationStatement.medication[x] | Medication.code</code></td>
    <td rowspan="9">See the <a href="https://build.fhir.org/ig/hl7au/au-fhir-core/medicine-information.html">Medicine Information</a> guidance page in AU Core.</td>
  </tr>
  <tr>
    <td colspan="2">Clinical indication</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td><code>MedicationStatement.reasonCode | MedicationStatement.reasonReference</code></td>
  </tr>
  <tr>
    <td colspan="2">Strength</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a> | <a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
    <td><code>MedicationStatement.medication[x] | Medication.code | Medication.ingredient</code></td>
  </tr>
  <tr>
    <td colspan="2">Form</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a> | <a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
    <td><code>MedicationStatement.medication[x] | Medication.form</code></td>
  </tr>
  <tr>
    <td colspan="2">Dose amount</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td><code>MedicationStatement.dosage.doseAndRate</code></td>
  </tr>
  <tr>
    <td colspan="2">Route of administration</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td><code>MedicationStatement.dosage.route</code></td>
  </tr>
  <tr>
    <td colspan="2">Dose timing</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td><code>MedicationStatement.dosage.timing</code></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td><code>MedicationStatement.note</code></td>
  </tr>
  <tr>
    <td colspan="2">Date of assertion</td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td><code>MedicationStatement.dateAsserted</code></td>
  </tr>
  <tr>
    <td rowspan="7">Problem/Diagnosis summary</td>
    <td colspan="2">Problem / Diagnosis name</td>
    <td rowspan="7">Problems | History of Past Problems</td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td><code>Condition.code</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Body site</td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td><code>Condition.code</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date/time of onset</td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td><code>Condition.onsetDateTime</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date/time of resolution</td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td><code>Condition.abatementDateTime</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Status</td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td><code>Condition.clinicalStatus</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td><code>Condition.note</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Last updated</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td rowspan="5">Procedure</td>
    <td colspan="2">Procedure name</td>
    <td rowspan="5">History of Procedures</td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td><code>Procedure.code</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Clinical indication</td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td><code>Procedure.reasonCode | Procedure.reasonReference[x]</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Body site/laterality</td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td><code>Procedure.code</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date/time performed</td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td><code>Procedure.performed[x] | Procedure.performedDateTime</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td><code>Procedure.note</code></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="4">Sex and gender summary</td>
    <td colspan="2">Sex assigned at birth</td>
    <td rowspan="4">N/A</td>
    <td><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
    <td><code>Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-recordedSexOrGender')</code></td>
    <td>The <a href="http://hl7.org/fhir/StructureDefinition/individual-recordedSexOrGender">Person Recorded Sex or Gender extension</a> is profiled by <a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-rsg-sexassignedab.html">AU Core Sex Assigned At Birth (RSG)</a> to represent the concept of Sex assigned at birth.</td>
  </tr>
  <tr>
    <td colspan="2">Gender identity</td>
    <td><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
    <td><code>Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-genderIdentity')</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Pronoun/s</td>
    <td><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
    <td><code>Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-pronouns')</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Last updated</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td rowspan="4">Vaccination</td>
    <td colspan="2">Vaccine name</td>
    <td rowspan="4">Immunizations</td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td><code>Immunization.vaccineCode</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Sequence</td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td><code>Immunization.protocolApplied.doseNumber[x]</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date of administration</td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td><code>Immunization.occurenceDateTime</code></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td><code>Immunization.note</code></td>
    <td></td>
  </tr>
  <tr style="background-color: #f2f2f2;">
    <th>AUCDI Data Group</th>
    <th colspan="2">AUCDI Data Element</th>
    <th>AU PS Document Section</th>
    <th>IPS Profile(s)</th>
    <th>FHIR Path</th>
    <th>Comment</th>
  </tr>
  <tr>
    <td rowspan="5">Es@mated Date of Delivery (EDD) summary</td>
    <td colspan="2">EDD by menstrual cycle</td>
    <td rowspan="5">History of pregnancy</td>
    <td><a href="https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-edd-uv-ips.html">Observation Pregnancy - Expected Delivery Date (IPS)</a></td>
    <td><code>Observation.valueDateTime</code></td>
    <td>This data group maps to an IPS profile; This AUCDI data group is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td colspan="2">Date of ultrasound</td>
    <td><a href="https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-edd-uv-ips.html">Observation Pregnancy - Expected Delivery Date (IPS)</a></td>
    <td><code>Observation.effectiveDateTime</code></td>
    <td rowspan="2">AUCDI elements Date of ultrasound and Estimated data of delivery by ultrasound would be grouped together in the same Observation, separate to Estimated data of delivery by menstrual cycle.</td>
  </tr>
  <tr>
    <td colspan="2">EDD by ultrasound</td>
    <td><a href="https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-edd-uv-ips.html">Observation Pregnancy - Expected Delivery Date (IPS)</a></td>
    <td><code>Observation.valueDateTime</code></td>
  </tr>
  <tr>
    <td colspan="2">Last update</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td colspan="2">Gestation by ultrasound</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td rowspan="3">Pregnancy assertion</td>
    <td colspan="2">Pregnancy assertion</td>
    <td rowspan="3">History of pregnancy</td>
    <td><a href="https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-status-uv-ips.html">Observation Pregnancy - Status (IPS)</a></td>
    <td><code>Observation.valueCodeableConcept</code></td>
    <td rowspan="3">This data group maps to an IPS profile; This AUCDI data group is a <a href="future.html#future-candidate-requirements-under-consideration">Future Candidate Requirement Under Consideration</a>.</td>
  </tr>
  <tr>
    <td colspan="2">Justification</td>
     | <td><a href="https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-status-uv-ips.html">Observation Pregnancy - Status (IPS)</a></td>
    <td><code>Observation.note</code></td>
  </tr>
  <tr>
    <td colspan="2">Date of assertion</td>
     | <td><a href="https://build.fhir.org/ig/HL7/fhir-ips/StructureDefinition-Observation-pregnancy-status-uv-ips.html">Observation Pregnancy - Status (IPS)</a></td>
    <td><code>Observation.effectiveDateTime</code></td>
  </tr>
</tbody>
</table>