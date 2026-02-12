The following examples are published with this guide and all are available as a downloadable as zip file [here](downloads.html#examples).

{% include nonnormative-example-boilerplate.md %}

In addition to the examples defined in this implementation, synthetic (realistic but not real) test data for developers and testers that conforms to HL7 Australia FHIR implementation guides is maintained in the [HL7 AU FHIR Test Data](https://github.com/hl7au/au-fhir-test-data) repository. 

The AU PS Bundle examples include both technically focused examples intended to demonstrate specific features of AU PS profiles (e.g. `Composition.section.emptyReason`) and examples that demonstrate technical and clinical use case aspects that conform to AU PS requirements.  
Data within the use cases examples (e.g. medications) is provided by the [Sparked Patient Summary Clinical Focus Group](https://sparked.csiro.au/index.php/design-groups/).

### Bundle Examples
The table below identifies examples defined in this implementation guide.

How to read this table:
<ul>
  <li><strong>Column headers</strong>: AU PS Bundle example name, linking to the rendered example in this guide.</li>
  <li><strong>Use Case row</strong>: Links to the relevant Use Cases page in this guide, where applicable.</li>
  <li><strong>Element rows</strong>: Composition elements are included only where AU PS allows reference to other profiles or resources. Elements that allow only one reference type are not listed (e.g. <code>Composition.subject</code>). <br> Cells show how the element is represented in each example, either by identifying the AU PS profile referenced in the Bundle or by identifying a specific Composition element used in the example (e.g. `emptyReason`).</li>
  <li><strong>-</strong>: The example does not include this element.</li>
</ul>

<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
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
        <tr>
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
            <td><code>emptyReason</code></td>
            <td>AU PS Condition</td>
            <td>AU PS Condition</td>
            <td>AU PS Condition</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionAllergies</code></td>
            <td>AU PS AllergyIntolerance</td>
            <td>AU PS AllergyIntolerance</td>
            <td><code>emptyReason</code></td>
            <td>AU PS AllergyIntolerance</td>
            <td>AU PS AllergyIntolerance</td>
            <td>AU PS AllergyIntolerance</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionMedications</code></td>
            <td>AU PS MedicationStatement</td>
            <td>AU PS MedicationStatement</td>
            <td><code>emptyReason</code></td>
            <td>AU PS MedicationRequest</td>
            <td>AU PS MedicationStatement</td>
            <td>AU PS MedicationStatement</td>
        </tr>
        <tr>
            <td><code>Composition.section:sectionImmunizations</code></td>
            <td>-</td>
            <td>-</td>
            <td><code>emptyReason</code></td>
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



### Missing Data and Suppressed Data
The table below identifies examples defined in this implementation guide that demonstrate missing data or suppressed data.

How to read this table:
<ul>
  <li><strong>Column headers</strong>: AU PS Bundle example name, linking to the rendered example in this guide.</li>
  <li><strong>Row groups</strong>: Indicate whether the example is demonstrating missing data or suppressed data.</li>
  <li><strong>Element rows</strong>: Identify the element(s) in the example that demonstrate the missing or suppressed data.</li>
  <li><strong>-</strong>: The example does not represent missing or suppressed data.</li>
</ul>


<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th>AU PS Bundle example</th>
            <th><a href="Bundle-aups-section-emptyreason.html">Section empty reason</a></th>
            <th><a href="Bundle-aups-gpvisit-retrieval.html">Jeramy 27 May</a></th>
            <th><a href="Bundle-aups-referral-endoconsult-autogen.html">Joyce 07 November 2024</a></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="3"><strong>Missing Data</strong></td>
            <td rowspan="3"><code>Patient.birthDate</code></td>
            <td><code>MedicationRequest.authoredOn</code></td>
            <td rowspan="3">Observation.performer</td>
        </tr>
        <tr>
            <td><code>Immunization.occurrenceDateTime</code></td>
        </tr>
        <tr>
            <td><code>Observation.performer</code></td>
        </tr>
        <tr>
            <td rowspan="2"><strong>Suppressed Data</strong></td>
            <td><code>Patient.identifier</code></td>
            <td rowspan="2">-</td>
            <td rowspan="2">-</td>
        </tr>
        <tr>
            <td><code>Patient.gender</code></td>
        </tr>
    </tbody>
</table>