[Australian Core Data for Interoperability (AUCDI)](https://sparked.csiro.au/index.php/sparked-products-resources/australian-core-data-for-interoperability/aucdi-release-1/) is the product of a national clinician focussed requirements gathering project operating as part of the [Sparked AU FHIR Accelerator](https://sparked.csiro.au/).  The AUCDI outputs form a set of data requirements to be considered and referred to as part of the development and definition of AU Patient Summary. 

[AUCDI Release 2 Patient Summary component – Draft for Community Comment](https://sparked.csiro.au/index.php/sparked-products-resources/australian-core-data-for-interoperability/aucdi-release-2-patient-summary-community-comment/) has been released for review. This component version of AUCDI contains only Patient Summary content to allow a focused review and support an iterative development process of AUCDI. A full AUCDI Release 2, which supersedes AUCDI Release 1, will be published in June 2025, containing all of the content from AUCDI Release 1 plus the content from this component release. 

  <div> 
    <img src="aucdi2ps.png" alt="AUCDI and AU Patient Summary Development Approach" style="width:55%"/>
  </div>
*Figure 1: AUCDI and AU Patient Summary Development Approach*
<br/><br/>

An interpretation of AUCDI clinical information requirements through community consensus is undertaken to define support for the exchange of clinical and administrative data within technical constraints. Note that:
* In any particular release, AU Core or AU Patient Summary may not cover all AUCDI data concepts, especially when AUCDI data concepts are not supported in existing systems.
* AU Patient Summary includes exchange for concepts that are commonly implemented in systems and not included in AUCDI e.g. Patient.name, Practitioner.identifier, Procedure.encounter. 
* AU Patient Summary includes exchange for clinical concepts not yet included in AUCDI, e.g. MedicationRequest, which are included through reference to IPS or AU Core
* AU Patient Summary includes data elements not included in AUCDI that are required to make FHIR implementable e.g. Observation.status, MedicationRequest.intent, Provenance.

### AUCDI mappings into AU Patient Summary

The table below shows the relationship between the AUCDI Data Groups and Elements included in [AUCDI Release 2 Patient Summary component – Draft for Community Comment](https://sparked.csiro.au/index.php/sparked-products-resources/australian-core-data-for-interoperability/aucdi-release-2-patient-summary-community-comment/), AU Core profiles, and AU Patient Summary profiles.<br/>

Column attribute descriptions are as follows:
- **AUCDI Data Group**: The name of the AUCDI data group.
- **AUCDI Data Element**: The name of the AUCDI data element within an AUCDI data group.
- **AU Core Profile(s)**: The title of the AU Core profile relevant for exchange.
- **AU Patient Summary Profile(s)**: The title of the AU Patient Summary profile relevant for exchange.
- **FHIR Path**: The [FHIRPath expression](https://build.fhir.org/ig/HL7/FHIRPath/) to the FHIR element relevant for exchange, i.e. the FHIR element that can be populated with data from a source system that represents the clinical concept expressed in the AUCDI data element. 
- **Comment**: Additional information about the mapping including an explanation of where an element or group is not yet mapped.

<table border="1" cellspacing="0" cellpadding="0" width="100%">
<thead>
  <tr style="background-color: #f2f2f2;">
    <th>AUCDI Data Group</th>
    <th colspan="2">AUCDI Data Element</th>
    <th>AU Core Profile(s)</th>
    <th>AU Patient Summary Profile(s)</th>
    <th>FHIR Path</th>
    <th>Comment</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="6">Adverse reaction risk summary</td>
    <td colspan="2">Substance name</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html">AU Core AllergyIntolerance</a></td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td>AllergyIntolerance.code</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date/time of onset of first reaction</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html">AU Core AllergyIntolerance</a></td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td>TBD</td>
    <td>This data element is added to AUCDI R2; work is underway to map to AU Core.</td>
  </tr>
  <tr>
    <td colspan="2">Manifestation</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html">AU Core AllergyIntolerance</a></td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td>AllergyInterolance.reaction</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Severity of reaction</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html">AU Core AllergyIntolerance</a></td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td>TBD</td>
    <td>This data element is added to AUCDI R2; work is underway to map to AU Core.</td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html">AU Core AllergyIntolerance</a></td>
    <td><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
    <td>AllergyIntolerance.note</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Last updated</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a Future Candidate Requirement Under Consideration. Future versions of AU Core will develop and test approaches to addressing Last Updated.</td>
  </tr>
  <tr>
    <td rowspan="7">Problem/Diagnosis summary</td>
    <td colspan="2">Problem / Diagnosis name</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html">AU Core Condition</a></td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td>Condition.code</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Body site/laterality</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html">AU Core Condition</a></td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td>Condition.code</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date/time of onset</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html">AU Core Condition</a></td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td>TBD</td>
    <td>This data element is added to AUCDI R2; work is underway to map to AU Core.</td>
  </tr>
  <tr>
    <td colspan="2">Date/time of resolution</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html">AU Core Condition</a></td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td>TBD</td>
    <td>This data element is added to AUCDI R2; work is underway to map to AU Core.</td>
  </tr>
  <tr>
    <td colspan="2">Status</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html">AU Core Condition</a></td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td>Condition.clinicalStatus</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html">AU Core Condition</a></td>
    <td><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
    <td>Condition.note</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Last updated</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a Future Candidate Requirement Under Consideration. Future versions of AU Core will develop and test approaches to addressing Last Updated.</td>
  </tr>
  <tr>
    <td rowspan="5">Procedure completed event</td>
    <td colspan="2">Procedure name</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html">AU Core Procedure</a></td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td>Procedure.code</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Clinical indication</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html">AU Core Procedure</a></td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td>Procedure.reasonCode | Procedure.reasonReference[x]</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Body site/laterality</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html">AU Core Procedure</a></td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td>Procedure.code</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date performed</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html">AU Core Procedure</a></td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td>Procedure.performed[x] | Procedure.performedDateTime</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html">AU Core Procedure</a></td>
    <td><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
    <td>Procedure.note</td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="4">Vaccination administered event</td>
    <td colspan="2">Vaccine name</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-immunization.html">AU Core Immunization</a></td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td>Immunization.vaccineCode</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Sequence number</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-immunization.html">AU Core Immunization</a></td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td>Immunization.protocolApplied.doseNumber[x]</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Date of administration</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-immunization.html">AU Core Immunization</a></td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td>Immunization.occurenceDateTime</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-immunization.html">AU Core Immunization</a></td>
    <td><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
    <td>Immunization.note</td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="9">Medication use statement</td>
    <td colspan="2">Medication name</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a> | <a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medication.html">AU Core Medication</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a> | <a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
    <td>MedicationStatement.medication[x] | Medication.code</td>
    <td rowspan="9">See <a href="medicine-information.html">Medicine Information</a> guidance.</td>
  </tr>
  <tr>
    <td colspan="2">Clinical indication</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td>MedicationStatement.reasonCode | MedicationStatement.reasonReference</td>
  </tr>
  <tr>
    <td colspan="2">Strength</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a> | <a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medication.html">AU Core Medication</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a> | <a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
    <td>MedicationStatement.medication[x] | Medication.code | Medication.ingredient</td>
  </tr>
  <tr>
    <td colspan="2">Form</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a> | <a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medication.html">AU Core Medication</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a> | <a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
    <td>MedicationStatement.medication[x] | Medication.form</td>
  </tr>
  <tr>
    <td colspan="2">Dose amount</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td>MedicationStatement.dosage.doseAndRate</td>
  </tr>
  <tr>
    <td colspan="2">Route of administration</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td>MedicationStatement.dosage.route</td>
  </tr>
  <tr>
    <td colspan="2">Dose timing</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td>MedicationStatement.dosage.timing</td>
  </tr>
  <tr>
    <td colspan="2">Comment</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td>MedicationStatement.note</td>
  </tr>
  <tr>
    <td colspan="2">Date of assertion</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html">AU Core MedicationStatement</a></td>
    <td><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
    <td>MedicationStatement.dateAsserted</td>
  </tr>
  <tr>
    <td rowspan="4">Sex and gender summary</td>
    <td colspan="2">Sex assigned at birth</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-patient.html">AU Core Patient</a></td>
    <td><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
    <td>Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-recordedSexOrGender')</td>
    <td>The <a href="http://hl7.org/fhir/StructureDefinition/individual-recordedSexOrGender">Person Recorded Sex or Gender extension</a> is profiled by <a href="StructureDefinition-au-core-rsg-sexassignedab.html">AU Core Sex Assigned At Birth (RSG)</a> to represent the concept of Sex assigned at birth.</td>
  </tr>
  <tr>
    <td colspan="2">Gender identity</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-patient.html">AU Core Patient</a></td>
    <td><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
    <td>Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-genderIdentity')</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Pronoun/s</td>
    <td><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-patient.html">AU Core Patient</a></td>
    <td><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
    <td>Patient.extension.where(url='http://hl7.org/fhir/StructureDefinition/individual-pronouns')</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2">Last updated</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>This AUCDI element is a Future Candidate Requirement Under Consideration. Future versions of AU Core will develop and test approaches to addressing Last Updated.</td>
  </tr>
  <tr>
    <td rowspan="3">Last menstrual period assertion</td>
    <td colspan="2">Date of onset</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
    <td rowspan="3">This data group is added to AUCDI R2 and does not yet have an agreed mapping to AU Core. Outcomes from the scoping workshops for AU Core R2 and Patient Summary R1 indicate that this data group will be deferred to a later release.</td>
  </tr>
  <tr>
    <td colspan="2">Certainty</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
  </tr>
  <tr>
    <td colspan="2">Date of assertion</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
  </tr>
  <tr>
    <td rowspan="3">Pregnancy assertion</td>
    <td colspan="2">Pregnancy assertion</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
    <td rowspan="3">This data group is added to AUCDI R2 and does not yet have an agreed mapping to AU Core. Outcomes from the scoping workshops for AU Core R2 and Patient Summary R1 indicate that this data group will be deferred to a later release.</td>
  </tr>
  <tr>
    <td colspan="2">Justification</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
  </tr>
  <tr>
    <td colspan="2">Date of assertion</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
  </tr>
  <tr>
    <td rowspan="3">Estimated date of delivery summary</td>
    <td colspan="2">EDD by cycle</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
    <td rowspan="3">This data group is added to AUCDI R2 and does not yet have an agreed mapping to AU Core. Outcomes from the scoping workshops for AU Core R2 and Patient Summary R1 indicate that this data group will be deferred to a later release.</td>
  </tr>
  <tr>
    <td colspan="2">EDD by ultrasound</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
  </tr>
  <tr>
    <td colspan="2">Last update</td>
    <td>TBD</td>
    <td>TBD</td>
    <td>TBD</td>
  </tr>
</tbody>
</table>