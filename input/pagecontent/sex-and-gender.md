This page addresses how sex and gender related concepts can be structured in FHIR and conformant to AU Patient Summary (AU PS).

AU PS references AU Base and AU Core profiles which represent sex and gender concepts. AU PS places *Must Support* on some concepts through the application of AU Core rules and inherits sex and gender related elements localised in AU Base, which has considered the logical data element models provided by [HL7 International’s Cross Paradigm Implementation Guide: Gender Harmony - Sex and Gender Representation, Edition 1 specification](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/).

The table below provides an overview of the sex and gender concepts that are included in AU PS through definition, or by reference to AU Base.

**Legend:**

<img src="green_checkmark.png" width="20"/> **Supported**: The sex or gender related concept is marked as *Must Support*.

<img src="orange_checkmark.png" width="20"/> **Localised**: The sex or gender related concept is localised for use in an Australian context but is not marked as *Must Support*.

<img src="minus_symbol.png" width="20"/> **Not localised**: The sex or gender related concept is not localised for use in an Australian context.


<table border="1" style="width: 100%; margin: auto; border-collapse: collapse;">
    <thead>
        <tr>
            <th style="width: 25%; text-align: center; vertical-align: middle;">Sex and Gender Concept</th>
            <th style="width: 25%; text-align: center; vertical-align: middle;"><a href="StructureDefinition-au-ps-patient.html">AU PS Patient</a></th>
            <th style="width: 25%; text-align: center; vertical-align: middle;"><a href="StructureDefinition-au-ps-practitioner.html">AU PS Practitioner</a></th>
            <th style="width: 25%; text-align: center; vertical-align: middle;"><a href="StructureDefinition-au-ps-relatedperson.html">AU PS RelatedPerson</a></th>
        </tr>
    </thead>
    <tbody>
          <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="sex-and-gender.html#administrative-gender-patientgender">Administrative Gender (Patient.gender)</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="minus_symbol.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="sex-and-gender.html#name-to-use">Name to Use</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="sex-and-gender.html#pronouns">Pronouns</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="sex-and-gender.html#gender-identity">Gender Identity</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="green_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#recorded-sex-or-gender">Recorded Sex or Gender</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
        <tr>
            <td style="width: 25%; text-align: left; vertical-align: middle;"><a href="https://build.fhir.org/ig/hl7au/au-fhir-core/sex-and-gender.html#sex-assigned-at-birth">Sex Assigned at Birth</a></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
            <td style="width: 25%; text-align: center; vertical-align: middle;"><img src="orange_checkmark.png" width="20"/></td>
        </tr>
    </tbody>
</table>


### Administrative Gender (Patient.gender)
AU PS Patient supports the exchange of Administrative Gender, i.e. the basic `Patient.gender` property, as a *Must Support* element in [AU PS Patient](StructureDefinition-au-ps-patient.html). As per AU Base, the `Patient.gender` value **SHALL** be regarded as a Recorded Sex or Gender. AU PS adopts without change, the implementation guidance defined in the [Administrative Gender (Patient.gender)](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#administrative-gender-patientgender) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.

### Name to Use
AU PS supports the exchange of the Name to Use data element (as defined in the [HL7 Gender Harmony IG](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)), `name.use` is a *Must Support* element in [AU PS Patient](StructureDefinition-au-ps-patient.html) and [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html). It is important to note that, `name.period` is not a *Must Support* element. AU PS adopts without change, the implementation guidance defined in the [Name to Use](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#name-to-use-ntu) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.

### Pronouns​
AU PS supports the exchange of the Pronouns data element (as defined in the [HL7 Gender Harmony IG](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)), the [Individual Pronouns](http://hl7.org/fhir/StructureDefinition/individual-pronouns) extension is a *Must Support* element in [AU PS Patient](StructureDefinition-au-ps-patient.html), with the value element of the extension constrained to be [Australian Pronouns](https://www.healthterminologies.gov.au/integration/R4/fhir/ValueSet/australian-pronouns-1) ([extensible](http://hl7.org/fhir/R4/terminologies.html#extensible)). AU PS adopts without change, the implementation guidance defined in the [Pronouns](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#pronouns) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.

### Gender Identity
AU PS supports the exchange of the Gender Identity data element (as defined in the [HL7 Gender Harmony IG](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)), the [Individual Gender Identity](http://hl7.org/fhir/StructureDefinition/individual-genderIdentity) extension is a *Must Support* element in [AU PS Patient](StructureDefinition-au-ps-patient.html), with the value element of the extension constrained to be [Gender Identity Response](https://healthterminologies.gov.au/fhir/ValueSet/gender-identity-response-1) ([extensible](http://hl7.org/fhir/R4/terminologies.html#extensible)). AU PS adopts without change, the implementation guidance defined in the [Gender Identity](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#gender-identity-gi) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.
