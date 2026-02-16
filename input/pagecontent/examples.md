The following examples are published with this guide and all are available as a downloadable as zip file [here](downloads.html#examples).

{% include nonnormative-example-boilerplate.md %}

In addition to the examples defined in this implementation guide, synthetic (realistic but not real) test data for developers and testers that conforms to HL7 Australia FHIR implementation guides is maintained in the [HL7 AU FHIR Test Data](https://github.com/hl7au/au-fhir-test-data) repository. 

### AU PS Bundle Examples
The examples included in this guide are AU PS documents (i.e. Bundles); standalone examples of AU PS profiles are not provided.

A set of examples are provided to demonstrate some parts of AU PS profiles (e.g. `Composition.section.emptyReason`, No Known X, Data Absent Reason extension) but are not intended to demonstrate clinical workflows or use cases:
- [Basic Summary](Bundle-aups-basicsummary.html)
- [No Known X](Bundle-aups-noknownx.html)
- [Section empty reason](Bundle-aups-section-emptyreason.html)

A set of examples demonstrate technical and clinical use case aspects, conforming to the AU PS requirements. Data within the use cases examples (e.g. medications) is provided by the [Sparked Patient Summary Clinical Focus Group](https://sparked.csiro.au/index.php/design-groups/):
- [Jeramy 27 May](Bundle-aups-gpvisit-retrieval.html)
- [Joyce 28 October](Bundle-aups-referral-endoconsult-curated.html)
- [Joyce 07 November 2024](Bundle-aups-referral-endoconsult-autogen.html)

The table below identifies some major characteristics of the examples defined in this IG, e.g. the profile a section entry or Composition element is populated with.

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr style="background-color: #f2f2f2;">
            <th>AU PS Bundle Example</th>
            <th><a href="Bundle-aups-basicsummary.html">Basic Summary</a></th>
            <th><a href="Bundle-aups-noknownx.html">No Known X</a></th>
            <th><a href="Bundle-aups-section-emptyreason.html">Section empty reason</a></th>
            <th><a href="Bundle-aups-gpvisit-retrieval.html">Jeramy 27 May</a></th>
            <th><a href="Bundle-aups-referral-endoconsult-curated.html">Joyce 28 October</a></th>
            <th><a href="Bundle-aups-referral-endoconsult-autogen.html">Joyce 07 November 2024</a></th>
        </tr>
    </thead>
    <tbody>
        <tr style="background-color: #f0f8ff;">
            <td><strong>Use Case</strong></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td><a href="uc-interstate.html">Interstate GP Visit</a></td>
            <td><a href="uc-referral.html">Referral to Specialist and Allied Health</a></td>
            <td><a href="uc-referral.html">Referral to Specialist and Allied Health</a></td>
        </tr>
        <tr>
            <td><code>Composition.author</code></td>
            <td>AU PS PractitionerRole</td>
            <td>AU PS PractitionerRole</td>
            <td>AU PS RelatedPerson</td>
            <td>AU PS Practitioner</td>
            <td>AU PS PractitionerRole</td>
            <td>Device</td>
        </tr>
        <tr>
            <td><code>Composition.attester</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>AU PS PractitionerRole</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionProblems</code></td>
            <td>AU PS Condition</td>
            <td>AU PS Condition</td>
            <td>emptyReason</td>
            <td>AU PS Condition</td>
            <td>AU PS Condition</td>
            <td>AU PS Condition</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionAllergies</code></td>
            <td>AU PS AllergyIntolerance</td>
            <td>AU PS AllergyIntolerance</td>
            <td>emptyReason</td>
            <td>AU PS AllergyIntolerance</td>
            <td>AU PS AllergyIntolerance</td>
            <td>AU PS AllergyIntolerance</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionMedications</code></td>
            <td>AU PS MedicationStatement</td>
            <td>AU PS MedicationStatement</td>
            <td>emptyReason</td>
            <td>AU PS MedicationRequest</td>
            <td>AU PS MedicationStatement</td>
            <td>AU PS MedicationStatement</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionImmunizations</code></td>
            <td>-</td>
            <td>-</td>
            <td>emptyReason</td>
            <td>AU PS Immunization</td>
            <td>AU PS Immunization</td>
            <td>AU PS Immunization</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionResults</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>AU PS Pathology Result</td>
            <td>-</td>
            <td>AU PS Pathology Result</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionProceduresHx</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>AU PS Procedure</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionMedicalDevices</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionAdvanceDirectives</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionAlerts</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionFunctionalStatus</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionPastProblems</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>AU PS Condition</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionPregnancyHx</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>Pregnancy - Status (IPS)</td>
            <td>Pregnancy - Status (IPS)</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionPatientStory</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionPlanOfCare</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionSocialHistory</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>AU PS Smoking Status</td>
            <td>AU PS Smoking Status</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionVitalSigns</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
        </tr>
        <tr>
            <td><code>Bundle.signature.who</code></td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>-</td>
            <td>PractitionerRole</td>
            <td>Device</td>
        </tr>
    </tbody>
</table>


#### Missing Data, Empty Sections, Known Absence of Data and Suppressed Data
The table below indicates the elements within examples that demonstrate apsects of [Missing Data, Empty Sections, Known Absence of Data](general-requirements.html#missing-data-empty-sections-known-absence-of-data). 

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr style="background-color: #f2f2f2;">
            <th>AU PS Bundle example</th>
            <th><a href="Bundle-aups-section-emptyreason.html">Section empty reason</a></th>
            <th><a href="Bundle-aups-gpvisit-retrieval.html">Jeramy 27 May</a></th>
            <th><a href="Bundle-aups-referral-endoconsult-autogen.html">Joyce 07 November 2024</a></th>
            <th><a href="Bundle-aups-noknownx.html">No Known X</a></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="3"><strong>Missing Data</strong></td>
            <td rowspan="3"><code>Patient.birthDate</code></td>
            <td><code>MedicationRequest.authoredOn</code></td>
            <td rowspan="3"><code>Observation.performer</code></td>
            <td rowspan="3">-</td>
        </tr>
        <tr>
            <td><code>Immunization.occurrenceDateTime</code></td>
        </tr>
        <tr>
            <td><code>Observation.performer</code></td>
        </tr>
        <tr>
            <td rowspan="4"><strong>Empty Sections</strong></td>
            <td><code>Composition.section:sectionProblems</code></td>
            <td rowspan="4">-</td>
            <td rowspan="4">-</td>
            <td rowspan="4">-</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionAllergies</code></td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionMedications</code></td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionImmunizations</code></td>
        </tr>
        <tr>
            <td rowspan="3"><strong>Known Absence of Data</strong></td>
            <td rowspan="3">-</td>
            <td rowspan="3">-</td>
            <td rowspan="3">-</td>
            <td><code>AllergyIntolerance.code</code></td>
        </tr>
        <tr>
            <td><code>MedicationStatement.medicationCodeableConcept</code></td>
        </tr>
        <tr>
            <td><code>MedicationStatement.medicationCodeableConcept</code></td>
        </tr>
        <tr>
            <td><code>Condition.code</code></td>
        </tr>
        <tr>
            <td rowspan="2"><strong>Suppressed Data</strong></td>
            <td><code>Patient.identifier</code></td>
            <td rowspan="2">-</td>
            <td rowspan="2">-</td>
            <td rowspan="2">-</td>
        </tr>
        <tr>
            <td><code>Patient.gender</code></td>
        </tr>
    </tbody>
</table>