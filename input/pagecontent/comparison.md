AU Patient Summary complies with, and leverages, national and international standards, in particular:
- [International Patient Access 1.0.0](https://hl7.org/fhir/uv/ipa/STU1/)
- [International Patient Summary Implementation Guide 2.0.0-ballot](https://hl7.org/fhir/uv/ips/2024Sep/)
- [AU Core Implementation Guide](https://build.fhir.org/ig/hl7au/au-fhir-core/)

Relationships between AU Patient Summary, AU Core, AUCDI, and the above key implementation guides is described in [Relationship with other IGs](relationship.html). 

Corresponding profiles, conformance requirements, and capability statements included in the key FHIR implementation guides were reviewed and considered during AU PS's development to ensure alignment, and to facilitate adoption of, this standard.

The below comparison evaluates AU Patient Summary conformance requirements with the key implementation guides identifying where compliance with AU Patient Summary satisfies the expectations established by the referenced implementation guide. 

### Profile comparison
As part of profile comparison, the requirements, constraints, and standards specified in a particular FHIR profile are evaluated. These requirements can include mandatory elements, must support elements, cardinality constraints, data types, terminology bindings, usage rules, extensions, rules on missing or suppressed data. 

The table below provides a profile only comparison from AU Patient Summary to profiles in key implementation guides. Compliance in the reverse direction is not guaranteed, i.e. a resource that is compliant with an International Patient Summary profile **MAY NOT** be compliant with AU Patient Summary.

**Legend:**

<img src="green_checkmark.svg.png" width="20"/> **Compliant**: An AU PS compliant resource meets all requirements of the compared profile.

<img src="orange_checkmark.svg.png" width="20"/> **Additional requirements**: An AU PS compliant resource is compatible, but additional changes may be needed to meet all requirements of the compared profile. Where additional requirements are identified, more information is provided in the sections below.

<img src="cross_red_circle.svg.png" width="20"/> **Incompatible**: An AU PS compliant resource is incompatible with the compared profile. A resource cannot be compliant to both. Where incompatible requirements are identified, more information is provided in the sections below.

<img src="minus_symbol.svg.png" width="20"/> **No equivalent profile**: No equivalent profile for comparison.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 25%; text-align: center; vertical-align: middle;">AU PS</th>
            <th style="width: 25%; text-align: center; vertical-align: middle;">International Patient Access 1.0.0</th>
            <th style="width: 25%; text-align: center; vertical-align: middle;">International Patient Summary 2.0.0 (ci-build)</th>
            <th style="width: 25%; text-align: center; vertical-align: middle;">AU Core (ci-build)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-allergyintolerance.html">AU PS AllergyIntolerance</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-bundle.html">AU PS Bundle</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-composition.html">AU PS Composition</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td rowspan="2" style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-condition.html">AU PS Condition</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td rowspan="2" style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td rowspan="2" style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: center; vertical-align: middle;">IPA-problem-list-item <img src="orange_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-encounter.html">AU PS Encounter</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-immunization.html">AU Core Immunization</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange)checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medication.html">AU PS Medication</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.svg.png" width="20"/><img src="cross_red_circle.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-organization.html">AU PS Organization</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-practitioner.html">AU PS Practitioner</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-practitionerrole.html">AU PS PractitionerRole</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="StructureDefinition-au-ps-procedure.html">AU PS Procedure</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-location.html">AU Core Location</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.svg.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-relatedperson.html">AU Base RelatedPerson</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.svg.png" width="20"/></td>
        </tr>
    </tbody>
</table>

#### International Patient Access
[International Patient Access 1.0.0](https://hl7.org/fhir/uv/ipa/STU1/) describes how an application acting on behalf of a patient can access patient information from a clinical records system using a FHIR-based API.

##### Incompatible requirements
The following IPA profile(s) contain incompatible requirements with the equivalent AU PS Profile. Implementers are advised to note that substantial code changes may be required to support these profiles.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 25%;">AU PS</th>
            <th style="width: 25%;">International Patient Access 1.0.0</th>
            <th style="width: 25%;">Element</th>
            <th style="width: 25%;">Incompatible requirements</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="width: 25%;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td style="width: 25%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-medicationrequest.html">IPA-MedicationRequest</a></td>
            <td style="width: 25%;">MedicationRequest.requester</td>
            <td style="width: 25%;">IPA prohibits reference to Organization and RelatedPerson resources.</td>
        </tr>
    </tbody>
</table>

##### Additional requirements
The following IPA profile(s) contain additional requirements. Implementers are advised to note that some code changes may be required to support these profiles.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 25%;">AU PS</th>
            <th style="width: 25%;">International Patient Access 1.0.0</th>
            <th style="width: 25%;">Element</th>
            <th style="width: 25%;">Additional requirements</th>
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
            <td style="width: 25%;"><a href="StructureDefinition-au-ps-immunization.html">AU PS Immunization</a></td>
            <td style="width: 25%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-immunization.html">IPA-Immunization</a></td>
            <td style="width: 25%;">Immunization.statusReason</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td style="width: 25%;"><a href="StructureDefinition-au-ps-medicationrequest.html">AU PS MedicationRequest</a></td>
            <td style="width: 25%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-medicationrequest.html">IPA-MedicationRequest</a></td>
            <td style="width: 25%;">MedicationRequest.reported[x]</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
            <td rowspan="4" style="width: 25%;"><a href="StructureDefinition-au-ps-medicationstatement.html">AU PS MedicationStatement</a></td>
            <td rowspan="4" style="width: 25%;"><a href="https://hl7.org/fhir/uv/ipa/STU1/StructureDefinition-ipa-medicationstatement.html">IPA-MedicationStatement</a></td>
            <td style="width: 25%;">MedicationStatement.status</td>
            <td style="width: 25%;"><i>Must Support</i> element in IPA.</td>
        </tr>
        <tr>
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