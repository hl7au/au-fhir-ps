{::options toc_levels="1..4"/}

AU Patient Summary (AU PS) complies with, and/or leverages, national and international standards, in particular:
- [International Patient Access 1.1.0](https://hl7.org/fhir/uv/ipa/STU1.1/)
- [International Patient Summary Implementation Guide 2.0.0](https://hl7.org/fhir/uv/ips/STU2/)
- [AU Core Implementation Guide 2.0.0](https://build.fhir.org/ig/hl7au/au-fhir-core/)
- [United States Patient Care Summary (US-PCS) Implementation Guide 1.0.0-ballot](https://build.fhir.org/ig/HL7/us-fhir-ps/en/index.html) 

Relationships between AU PS, AUCDI, and the above key implementation guides are described in [Relationship with other IGs](relationship.html). 

### Profile Comparison
As part of profile comparison, the requirements, constraints, and standards specified in a particular FHIR profile are evaluated. These requirements can include mandatory elements, *Must Support* elements, cardinality constraints, data types, terminology bindings, usage rules, extensions, rules on missing or suppressed data. 

The table below provides a profile only comparison from AU PS to profiles in key implementation guides. Compliance in the reverse direction is not guaranteed, i.e. a resource that is compliant with an International Patient Summary profile **MAY NOT** be compliant with AU PS.

The comparison considers **SHALL** and **SHOULD** requirements. **MAY** requirements are not compared.

**Legend:**

<img src="green_checkmark.png" width="20"/> **Compliant**: An AU PS compliant resource meets all requirements of the compared profile.

<img src="orange_checkmark.png" width="20"/> **Additional requirements**: An AU PS compliant resource is compatible, but additional changes may be needed to meet all requirements of the compared profile. Where additional requirements are identified, more information is provided in the sections below.

<img src="cross_red_circle.png" width="20"/> **Incompatible**: An AU PS compliant resource is incompatible with the compared profile. A resource cannot be compliant to both. Where incompatible requirements are identified, more information is provided in the sections below.

<img src="minus_symbol.png" width="20"/> **No equivalent profile**: No equivalent profile for comparison.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 20%; text-align: center; vertical-align: middle;">AU PS</th>
            <th style="width: 20%; text-align: center; vertical-align: middle;">IPA 1.1.0</th>
            <th style="width: 20%; text-align: center; vertical-align: middle;">IPS 2.0.0</th>
            <th style="width: 20%; text-align: center; vertical-align: middle;">AU Core 2.0.0</th>
            <th style="width: 20%; text-align: center; vertical-align: middle;">US-PCS 1.0.0-ballot</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-bundle.html">AU PS Bundle</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-composition.html">AU PS Composition</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td rowspan="2" style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td rowspan="2" style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td rowspan="2" style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td rowspan="2" style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: center; vertical-align: middle;">IPA-problem-list-item <img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-encounter.html">AU PS Encounter</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-organization.html">AU PS Organization</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-diagnosticresult-path.html">AU PS Pathology Result Observation</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-practitioner.html">AU PS Practitioner</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-practitionerrole.html">AU PS PractitionerRole</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
         <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-relatedperson.html">AU PS RelatedPerson</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 20%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-smokingstatus.html">AU PS Smoking Status</a></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 20%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
    </tbody>
</table>

#### IPA Profile Additional Requirements
The following IPA profile(s) contain additional requirements. Implementers are advised to note that some code changes may be required to support these profiles.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 20%;">AU PS Profile</th>
            <th style="width: 20%;">IPA 1.1.0 Profile</th>
            <th style="width: 20%;">Element</th>
            <th style="width: 20%;">IPA Profile Additional requirements</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="width: 20%;"><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
            <td style="width: 20%;"><a href="https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-problem-list-item.html">IPA-problem-list-item</a></td>
            <td style="width: 20%;">Condition.category</td>
            <td style="width: 20%;">Requires category of 'problem-list-item'.</td>
        </tr>
        <tr>
            <td style="width: 20%;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td style="width: 20%;"><a href="https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-medicationrequest.html">IPA-MedicationRequest</a></td>
            <td style="width: 20%;">MedicationRequest.reported[x]</td>
            <td style="width: 20%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td rowspan="3" style="width: 20%;"><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
            <td rowspan="3" style="width: 20%;"><a href="https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-medicationstatement.html">IPA-MedicationStatement</a></td>
            <td style="width: 20%;">MedicationStatement.statusReason</td>
            <td style="width: 20%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationStatement.context</td>
            <td style="width: 20%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationStatement.informationSource</td>
            <td style="width: 20%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td rowspan="5" style="width: 20%;"><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
            <td rowspan="5" style="width: 20%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-patient.html">IPA-Patient</a></td>
            <td style="width: 20%;">Patient.identifier</td>
            <td style="width: 20%;">IPA requires all identifiers to have value (1..1), and at least one of system, type or assigner (ipa-pat-1).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.identifier.value</td>
            <td style="width: 20%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.active</td>
            <td style="width: 20%;">Element SHOULD be present if Patient.link is present (ipa-pat-4). <i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.name.text</td>
            <td style="width: 20%;">Sub-element SHOULD be present (ipa-pat-3).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.link</td>
            <td style="width: 20%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 20%;"><a href="StructureDefinition-au-ps-practitioner.html">AU PS Practitioner</a></td>
            <td style="width: 20%;"><a href="https://hl7.org/fhir/uv/ipa/STU1.1/StructureDefinition-ipa-practitioner.html">IPA-Practitioner</a></td>
            <td style="width: 20%;">Practitioner.name.text</td>
            <td style="width: 20%;">Sub-element SHOULD be present (ipa-pract-1).</td>
        </tr>
    </tbody>
</table>

##### Missing and Suppressed Data
AU PS compliant resources are compliant with IPA requirements for Missing Data. IPA does not include requirements for Suppressed Data.

##### Additional Profiles
This version of AU PS has no equivalent profile for the following IPA profiles:
- IPA-DocumentReference

#### US-PCS Profile Additional Requirements
The following US-PCS profile(s) contain additional requirements. Implementers are advised to note that some code changes may be required to support these profiles.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 20%;">AU PS Profile</th>
            <th style="width: 20%;">US-PCS 1.0.0-ballot</th>
            <th style="width: 20%;">Element</th>
            <th style="width: 20%;">US-PCS Profile Additional requirements</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="4" style="width: 20%;"><a href="StructureDefinition-au-ps-bundle.html">AU PS Bundle</a></td>
            <td rowspan="4" style="width: 20%;"><a href="https://build.fhir.org/ig/HL7/us-fhir-ps/en/StructureDefinition-Bundle-us-pcs.html">Bundle (US-PCS)</a></td>
            <td style="width: 20%;">Bundle.identifier</td>
            <td style="width: 20%;">US-PCS requires all identifiers to have system and value (1..1).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Bundle.entry.resource</td>
            <td style="width: 20%;">US-PCS requires all entries to have a resource (1..1). <i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Bundle</td>
            <td style="width: 20%;">US-PCS requires the Bundle timestamp to be the same or after the Composition date (clindoc-timestamp-ge-compoDate).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Bundle.signature</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td rowspan="20" style="width: 20%;"><a href="StructureDefinition-au-ps-composition.html">AU PS Composition</a></td>
            <td rowspan="20" style="width: 20%;"><a href="https://build.fhir.org/ig/HL7/us-fhir-ps/en/StructureDefinition-Composition-us-pcs.html">Composition (US-PCS)</a></td>
            <td style="width: 20%;">Composition.language</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS. Requires language of “en-US”.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:R5-Composition-version</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:data-enterer</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:informant</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:information-recipient</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:participant</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:consent</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:basedOn</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.extension:change-made</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.modifierExtension:R5-Composition-status</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.category</td>
            <td style="width: 20%;">US-PCS requires LOINC 107903-7 Clinical note. <i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.confidentiality</td>
            <td style="width: 20%;">US-PCS requires minimum of 1. <i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.custodian</td>
            <td style="width: 20%;">US-PCS requires minimum of 1.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.relatesTo</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.section[all slices].change-made</td>
            <td style="width: 20%;"><i>Must Support</i> element in US-PCS.</td>
        </tr>   
        <tr>
            <td style="width: 20%;">Composition.section:sectionEncounters</td>
            <td style="width: 20%;">US-PCS requires either section.entry or emptyReason (cmp-uspcs-1).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.section:sectionImmunizations</td>
            <td style="width: 20%;">US-PCS requires either section.entry or emptyReason (cmp-uspcs-1).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.section:sectionProceduresHx</td>
            <td style="width: 20%;">US-PCS requires either section.entry or emptyReason (cmp-uspcs-1).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition.section:sectionResults</td>
            <td style="width: 20%;">US-PCS requires either section.entry or emptyReason (cmp-uspcs-1).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Composition</td>
            <td style="width: 20%;">US-PCS prohibits participation types ENT (data enterer), INF (informant), IRCP (information recipient), PRCP (primary information recipient) and TRC (tracker) from being recorded in <a href="http://hl7.org/fhir/uv/fhir-clinical-document/StructureDefinition/ParticipantExtension">Participant Extension</a>; dedicated extensions shall be used instead (clindoc-limit-participantType).</td>
        </tr>      
    </tbody>
</table>

##### US Core 6.1.0 Profile Additional Requirements
The following US Core profile(s) contain additional requirements. Implementers are advised to note that some code changes may be required to support these profiles.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 20%;">AU PS Profile</th>
            <th style="width: 20%;">US Core 6.1.0</th>
            <th style="width: 20%;">Element</th>
            <th style="width: 20%;">US-PCS Profile Additional requirements</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2" style="width: 20%;"><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
            <td rowspan="2" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-allergyintolerance.html">US Core AllergyIntolerance</a></td>
            <td style="width: 20%;">AllergyIntolerance.code</td>
            <td style="width: 20%;">US-PCS extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.113762.1.4.1186.8/expansion">Common substances for allergy and intolerance documentation including refutations</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">AllergyIntolerance.reaction.manifestation</td>
            <td style="width: 20%;">US-PCS extensible binding to <a href="https://hl7.org/fhir/R4/valueset-clinical-findings.html">SNOMED CT Clinical Findings</a>.</td>
        </tr>
        <tr>
            <td rowspan="5" style="width: 20%;"><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
            <td rowspan="5" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-condition-problems-health-concerns.html">US Core Condition Problems and Health Concerns Profile</a></td>
            <td style="width: 20%;">Condition.category</td>
            <td style="width: 20%;">US Core requires category of 'problem-list-item' or 'health-concern'.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Condition.code</td>
            <td style="width: 20%;">US-PCS extensible binding to <a href="https://hl7.org/fhir/us/core/STU6.1/ValueSet-us-core-condition-code.html">US Core Condition Code</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Condition.assertedDate</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Condition.abatement[x]</td>
            <td style="width: 20%;">Type choice dateTime is flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Condition.recordedDate</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td rowspan="7" style="width: 20%;"><a href="StructureDefinition-au-ps-encounter.html">AU PS Encounter</a></td>
            <td rowspan="7" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-encounter.html">US Core Encounter Profile</a></td>
            <td style="width: 20%;">Encounter.type</td>
            <td style="width: 20%;">US Core requires minimum of 1. Element flagged as <i>Must Support</i> in US Core. US Core extensible binding to <a href="https://hl7.org/fhir/us/core/STU6.1/ValueSet-us-core-encounter-type.html">US Core Encounter Type</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Encounter.identifier</td>
            <td style="width: 20%;">US Core requires all identifiers to have system and value. Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Encounter.identifier.system</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Encounter.identifier.value</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Encounter.participant.period</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Encounter.hospitalization</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Encounter.hospitalization.dischargeDisposition</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>  
        <tr>
            <td rowspan="2" style="width: 20%;"><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
            <td rowspan="2" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-immunization.html">US Core Immunization Profile</a></td>
            <td style="width: 20%;">Immunization.vaccineCode</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.113762.1.4.1010.6/expansion">CVX Vaccines Administered Vaccine Set</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Immunization.statusReason</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
<tr>
            <td style="width: 20%;"><a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
            <td style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-medication.html">US Core Medication Profile</a></td>
            <td style="width: 20%;">Medication.code</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.113762.1.4.1010.4/expansion">Medication Clinical Drug</a>.</td>
        </tr>
        <tr>
            <td rowspan="10" style="width: 20%;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td rowspan="10" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-medicationrequest.html">US Core MedicationRequest Profile</a></td>
            <td style="width: 20%;">MedicationRequest.medicationCodeableConcept</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.113762.1.4.1010.4/expansion">Medication Clinical Drug</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.category</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.reported[x]</td>
            <td style="width: 20%;">Type choice boolean and reference target Practitioner are flagged as <i>Must Support</i> in US Core. Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.requester</td>
            <td style="width: 20%;">Reference target Practitioner is flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>   
            <td style="width: 20%;">MedicationRequest.reasonCode</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://www.hl7.org/fhir/us/core/ValueSet-us-core-condition-code.html">US Core Condition Codes</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.dosageInstruction.doseAndRate</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.dosageInstruction.doseAndRate.dose[x]</td>
            <td style="width: 20%;">Type choice Quantity is flagged as <i>Must Support</i> in US Core. Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.dispenseRequest</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.dispenseRequest.numberOfRepeatsAllowed</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">MedicationRequest.dispenseRequest.quantity</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>  
    <tr>
            <td rowspan="7" style="width: 20%;"><a href="StructureDefinition-au-ps-organization.html">AU PS Organization</a></td>
            <td rowspan="7" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/tructureDefinition-us-core-organization.html">US Core Organization Profile</a></td>
            <td style="width: 20%;">Organization.active</td>
            <td style="width: 20%;">US Core requires minimum of 1. Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Organization.identifier</td>
            <td style="width: 20%;">Sub-elements flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Organization.address.line</td>
            <td style="width: 20%;">US Core allows maximum of 4. Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Organization.address.city</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Organization.address.state</td>
            <td style="width: 20%;">US Core extensible binding to <a href="http://terminology.hl7.org/ValueSet/USPS-State">USPS Two Letter Alphabetic Codes</a>. Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Organization.address.postalCode</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Organization.address.country</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
    </tr>  
    <tr>
            <td rowspan="3" style="width: 20%;"><a href="StructureDefinition-au-ps-diagnosticresult-path.html">AU PS Pathology Result Observation</a></td>
            <td rowspan="3" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-observation-lab.html">US Core Laboratory Result Observation Profile</a></td>
            <td style="width: 20%;">Observation.code</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://hl7.org/fhir/us/core/STU8/ValueSet-us-core-laboratory-test-codes.html">US Core Laboratory Test Codes</a>. </td>
        </tr>
        <tr>
            <td style="width: 20%;">Observation.referenceRange</td>
            <td style="width: 20%;">US Core requires SNOMED CT for coded quantity units (us-core-22).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Observation.value[x]</td>
            <td style="width: 20%;">US Core requires UCUM for coded quantity units (us-core-4). Type choices Quantity, CodeableConcept and string are flagged as <i>Must Support</i> in US Core.</td>
        </tr>    
    <tr>
            <td rowspan="9" style="width: 20%;"><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
            <td rowspan="9" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-patient.html">US Core Patient Profile</a></td>
            <td style="width: 20%;">Patient.identifier</td>
            <td style="width: 20%;">US Core requires all identifiers to have system and value.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.identifier.system</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.identifier.value</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.name</td>
            <td style="width: 20%;">US Core requires all name to have family or given or Data Absent Reason extension (us-core-6).</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.telecom</td>
            <td style="width: 20%;">US Core requires all telecom to have system and value.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.address.line</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.address.city</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.address.state</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://terminology.hl7.org/6.4.0/ValueSet-USPS-State.html">USPS Two Letter Alphabetic Codes</a>. Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Patient.address.postalCode</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>        
        <tr>
            <td rowspan="10" style="width: 20%;"><a href="StructureDefinition-au-ps-practitioner.html">AU PS Practitioner</a></td>
            <td rowspan="10" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-practitioner.html">US Core Practitioner Profile</a></td>
            <td style="width: 20%;">Practitioner.identifier</td>
             <td style="width: 20%;">US Core requires minimum of 1, and all identifiers to have system and value.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.identifier.system</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.identifier.value</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.telecom.system</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.telecom.value</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.address.line</td>
            <td style="width: 20%;">US Core allows maximum of 4. Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.address.city</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.address.state</td>
            <td style="width: 20%;">US Core extensible binding to <a href="http://terminology.hl7.org/ValueSet/USPS-State">USPS Two Letter Alphabetic Codes</a>. Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.address.postalCode</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Practitioner.address.country</td>
            <td style="width: 20%;">Sub-element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td rowspan="6" style="width: 20%;"><a href="StructureDefinition-au-ps-practitionerrole.html">AU PS PractitionerRole</a></td>
            <td rowspan="6" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-practitionerrole.html">US Core PractitionerRole Profile</a></td>
            <td style="width: 20%;">PractitionerRole.telecom, PractitionerRole.endpoint</td>
            <td style="width: 20%;">US Core requires telecom or endpoint to be present (pd-1).</td>
        </tr>
        <tr>
            <td style="width: 20%;">PractitionerRole.location</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">PractitionerRole.telecom</td>
            <td style="width: 20%;">US Core requires all telecom to have system and value.</td>
        </tr>
        <tr>
            <td style="width: 20%;">PractitionerRole.endpoint</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">PractitionerRole.code</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.113762.1.4.1099.30/expansion">Care Team Member Function</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">PractitionerRole.specialty</td>
            <td style="width: 20%;"> US Core extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.114222.4.11.1066/expansion">Healthcare Provider Taxonomy</a>.</td>
        </tr>  
        <tr>
            <td style="width: 20%;"><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
            <td style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-procedure.html">US Core Procedure Profile</a></td>
            <td style="width: 20%;">Procedure.code</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://hl7.org/fhir/us/core/STU6.1/ValueSet-us-core-procedure-code.html">US Core Procedure Codes</a>.</td>
        </tr>  
        <tr>
            <td style="width: 20%;"><a href="StructureDefinition-au-ps-relatedperson.html">AU PS RelatedPerson</a></td>
            <td style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU6.1/StructureDefinition-us-core-relatedperson.html">US Core RelatedPerson Profile</a></td>
            <td style="width: 20%;">RelatedPerson.active</td>
            <td style="width: 20%;">US Core requires minimum of 1. Element flagged as <i>Must Support</i> in US Core.</td>
        </tr>    
    <tr>
            <td rowspan="6" style="width: 20%;"><a href="StructureDefinition-au-ps-smokingstatus.html">AU PS Smoking Status</a></td>
            <td rowspan="6" style="width: 20%;"><a href="https://hl7.org/fhir/us/core/STU8/StructureDefinition-us-core-smokingstatus.html">US Core Smoking Status Observation Profile</a></td>
            <td style="width: 20%;">Observation.status</td>
            <td style="width: 20%;">US Core requires status of 'final' or 'entered-in-error'.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Observation.code</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.113762.1.4.1267.6/expansion">Smoking Status Type</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Observation.performer</td>
            <td style="width: 20%;">Element flagged as <i>Must Support</i> in US Core. Reference target Practitioner is flagged as <i>Must Support</i> in US Core.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Observation.value[x]</td>
            <td style="width: 20%;">US core requires minimum of 1.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Observation.value[x]:valueCodeableConcept</td>
            <td style="width: 20%;">US Core extensible binding to <a href="https://vsac.nlm.nih.gov/valueset/2.16.840.1.113762.1.4.1267.3/expansion">Smoking status comprehensive</a>.</td>
        </tr>
        <tr>
            <td style="width: 20%;">Observation.value[x]:valueQuantity</td>
            <td style="width: 20%;">This US Core profile supports capture of tobacco smoking consumption as well as smoking status; AU Core does not. An instantiation of Tobacco smoking consumption is considered an 'additional profile' not an additional requirement.</td>
        </tr>                              
    </tbody>
</table>

##### Missing and Suppressed Data
AU PS compliant resources are compliant with US-PCS requirements for Missing Data. US-PCS does not include requirements for Suppressed Data.

##### Additional Profiles
No additional profiles.

### Capability Statement Comparison

No comparison is undertaken. AU PS does not define any FHIR specific interactions - no CapabilityStatement is defined. 

Systems implementing AU Patient Summary **MAY** implement interactions defined in other CapabilityStatements, for example:
- [IPS Server Capability Statement](https://hl7.org/fhir/uv/ips/STU2/CapabilityStatement-ips-server.html)
- [International Patient Access Server CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-server.html)
- [International Patient Access Client CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-client.html)