{::options toc_levels="1..4"/}

AU Patient Summary (AU PS) complies with, and/or leverages, national and international standards, in particular:
- [International Patient Access 1.1.0](https://hl7.org/fhir/uv/ipa/STU1.1/)
- [International Patient Summary Implementation Guide 2.0.0](https://build.fhir.org/ig/HL7/fhir-ips/)
- [AU Core Implementation Guide 2.0.0](https://build.fhir.org/ig/hl7au/au-fhir-core/)

Relationships between AU PS, AU Core, AUCDI, and the above key implementation guides are described in [Relationship with other IGs](relationship.html). 

International Patient Access (IPA) and International Patient Summary (IPS) are specifically referenced, as these are the international specifications intended for use in patient summary use cases.

Corresponding profiles, conformance requirements, and capability statements included in the key FHIR implementation guides were reviewed and considered during AU PS's development to ensure alignment, and to facilitate adoption of, this standard.

The below comparison evaluates AU PS conformance requirements with the key implementation guides identifying where compliance with AU PS satisfies the expectations established by the referenced implementation guide. 

### Profile Comparison
As part of profile comparison, the requirements, constraints, and standards specified in a particular FHIR profile are evaluated. These requirements can include mandatory elements, *Must Support* elements, cardinality constraints, data types, terminology bindings, usage rules, extensions, rules on missing or suppressed data. 

The table below provides a profile only comparison from AU PS to profiles in key implementation guides. Compliance in the reverse direction is not guaranteed, i.e. a resource that is compliant with an International Patient Summary profile **MAY NOT** be compliant with AU PS.

**Legend:**

<img src="green_checkmark.png" width="20"/> **Compliant**: An AU PS compliant resource meets all requirements of the compared profile.

<img src="orange_checkmark.png" width="20"/> **Additional requirements**: An AU PS compliant resource is compatible, but additional changes may be needed to meet all requirements of the compared profile. Where additional requirements are identified, more information is provided in the sections below.

<img src="cross_red_circle.png" width="20"/> **Incompatible**: An AU PS compliant resource is incompatible with the compared profile. A resource cannot be compliant to both. Where incompatible requirements are identified, more information is provided in the sections below.

<img src="minus_symbol.png" width="20"/> **No equivalent profile**: No equivalent profile for comparison.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 25%; text-align: center; vertical-align: middle;">AU PS</th>
            <th style="width: 25%; text-align: center; vertical-align: middle;">IPA 1.1.0</th>
            <th style="width: 25%; text-align: center; vertical-align: middle;">IPS 2.0.0</th>
            <th style="width: 25%; text-align: center; vertical-align: middle;">AU Core 2.0.0</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-bundle.html">AU PS Bundle</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-composition.html">AU PS Composition</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
        </tr>
        <tr>
            <td rowspan="2" style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td rowspan="2" style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td rowspan="2" style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: center; vertical-align: middle;">IPA-problem-list-item <img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-encounter.html">AU PS Encounter</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-organization.html">AU PS Organization</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-diagnosticresult-path.html">AU PS Pathology Result Observation</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-practitioner.html">AU PS Practitioner</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-practitionerrole.html">AU PS PractitionerRole</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
         <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-relatedperson.html">AU PS RelatedPerson</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-smokingstatus.html">AU PS Smoking Status</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
    </tbody>
</table>

#### IPA Profile Additional Requirements
[IPA 1.1.0](https://hl7.org/fhir/uv/ipa/STU1.1/) describes how an application acting on behalf of a patient can access patient information from a clinical records system using a FHIR-based API.

##### Additional Requirements
The following IPA profile(s) contain additional requirements. Implementers are advised to note that some code changes may be required to support these profiles.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 25%;">AU PS Profile</th>
            <th style="width: 25%;">IPA 1.1.0 Profile</th>
            <th style="width: 25%;">Element</th>
            <th style="width: 25%;">IPA Profile Additional requirements</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="width: 25%;"><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
            <td style="width: 25%;"><a href="https://build.fhir.org/ig/HL7/fhir-ipa/StructureDefinition-ipa-problem-list-item.html">IPA-problem-list-item</a></td>
            <td style="width: 25%;">Condition.category</td>
            <td style="width: 25%;">Requires category of 'problem-list-item'.</td>
        </tr>
        <tr>
            <td style="width: 25%;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td style="width: 25%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-medicationrequest.html">IPA-MedicationRequest</a></td>
            <td style="width: 25%;">MedicationRequest.reported[x]</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td rowspan="3" style="width: 25%;"><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
            <td rowspan="3" style="width: 25%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-medicationstatement.html">IPA-MedicationStatement</a></td>
            <td style="width: 25%;">MedicationStatement.statusReason</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 25%;">MedicationStatement.context</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 25%;">MedicationStatement.informationSource</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td rowspan="3" style="width: 25%;"><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
            <td rowspan="3" style="width: 25%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-patient.html">IPA-Patient</a></td>
            <td style="width: 25%;">Patient.identifier.value</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 25%;">Patient.active</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 25%;">Patient.link</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
    </tbody>
</table>

##### Missing and Suppressed Data
AU PS compliant resources are compliant with IPA requirements for Missing Data. IPA does not include requirements for Suppressed Data.

### Capability Statement Comparison

No comparison is undertaken. AU PS does not define any FHIR specific interactions - no CapabilityStatement is defined. 

Systems implementing AU Patient Summary **MAY** implement interactions defined other CapabilityStatements, for example:
- [IPS Server Capability Statement](https://build.fhir.org/ig/HL7/fhir-ips/CapabilityStatement-ips-server.html)
- [International Patient Access Server CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-server.html)
- [International Patient Access Client CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-client.html)