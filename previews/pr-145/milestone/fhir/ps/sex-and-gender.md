# Sex and Gender - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**Guidance**](guidance.md)
* **Sex and Gender**

## Sex and Gender

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

This page addresses how sex and gender related concepts can be structured in FHIR and conformant to AU Patient Summary (AU PS).

AU PS is based on [IPS](https://hl7.org/fhir/uv/ips/STU2/index.html) and [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core). AU PS profiles inherit **Must Support** flags on sex and gender related elements from AU Core profiles, and inherit the localisation of these elements from AU Base. Work in AU Base has considered the logical data element models provided by [HL7 International’s Cross Paradigm Implementation Guide: Gender Harmony - Sex and Gender Representation, Edition 1 specification (HL7 Gender Harmony IG)](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/).

The IPS seeks to align with the [HL7 Gender Harmony IG](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/), and includes in the [Patient (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Patient-uv-ips.html) profile a number of sex and gender related elements; these inclusions are fully aligned to the work in AU Base, AU Core, and AU PS.

The table below provides an overview of the sex and gender concepts that are included in AU PS.

**Legend:**

![](green_checkmark.png) **Supported**: The sex or gender related concept is marked as **Must Support**.

![](orange_checkmark.png) **Localised**: The sex or gender related concept is localised for use in an Australian context but is not marked as **Must Support**.

![](blue_checkmark.png) **Not Localised**: The sex or gender related concept is relevant and not yet localised for use in an Australian context.

![](minus_symbol.png) **Not Applicable**: This sex or gender related concept is not applicable for use with this resource type.

| | | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| [AU PSPatient](StructureDefinition-au-ps-patient.md) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](green_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) |
| [AU PS Practitioner](StructureDefinition-au-ps-practitioner.md) | ![](blue_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](minus_symbol.png) |
| [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.md) | ![](blue_checkmark.png) | ![](green_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](orange_checkmark.png) | ![](minus_symbol.png) |
| [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.md) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](orange_checkmark.png) |
| [AU PS Procedure](StructureDefinition-au-ps-procedure.md) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](minus_symbol.png) | ![](orange_checkmark.png) |

### Administrative Gender (Patient.gender)

AU PS Patient supports the exchange of Administrative Gender, i.e. the basic `Patient.gender` property, as a **Must Support** element in [AU PS Patient](StructureDefinition-au-ps-patient.md). As per AU Base, the `Patient.gender` value **SHALL** be regarded as a Recorded Sex or Gender. AU PS adopts without change, the implementation guidance defined in the [Administrative Gender (Patient.gender)](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#administrative-gender-patientgender) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.

### Name to Use (NtU)

AU PS supports the exchange of the Name to Use data element (as defined in the [HL7 Gender Harmony IG](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)), `name.use` is a **Must Support** element in [AU PS Patient](StructureDefinition-au-ps-patient.md) and [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.md). It is important to note that `name.period` is not a **Must Support** element. AU PS adopts without change, the implementation guidance defined in the [Name to Use (NtU)](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#name-to-use-ntu) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.

### Pronouns​

AU PS supports the exchange of the Pronouns data element (as defined in the [HL7 Gender Harmony IG](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)), the [Individual Pronouns](http://hl7.org/fhir/StructureDefinition/individual-pronouns) extension is a **Must Support** element in [AU PS Patient](StructureDefinition-au-ps-patient.md), with the value element of the extension constrained to be [Australian Pronouns](https://www.healthterminologies.gov.au/integration/R4/fhir/ValueSet/australian-pronouns-1) ([extensible](http://hl7.org/fhir/R4/terminologies.html#extensible)). AU PS adopts without change, the implementation guidance defined in the [Pronouns](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#pronouns) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.

### Gender Identity (GI)

AU PS supports the exchange of the Gender Identity data element (as defined in the [HL7 Gender Harmony IG](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)), the [Individual Gender Identity](http://hl7.org/fhir/StructureDefinition/individual-genderIdentity) extension is a **Must Support** element in [AU PS Patient](StructureDefinition-au-ps-patient.md), with the value element of the extension constrained to be [Gender Identity Response](https://healthterminologies.gov.au/fhir/ValueSet/gender-identity-response-1) ([extensible](http://hl7.org/fhir/R4/terminologies.html#extensible)). AU PS adopts without change, the implementation guidance defined in the [Gender Identity (GI)](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#gender-identity-gi) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page.

### Recorded Sex or Gender

In AU PS, Recorded Sex or Gender is not **Must Support**. See the implementation guidance defined in the [Recorded Sex or Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#recorded-sex-or-gender) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page for more information.

### Sex Assigned at Birth

In AU PS, Sex Assigned at Birth is not **Must Support**. See the implementation guidance defined in the [Sex Assigned at Birth](https://build.fhir.org/ig/hl7au/au-fhir-core/sex-and-gender.html#sex-assigned-at-birth) section of the AU Core [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-core/sex-and-gender.html) page for more information.

### Sex Parameter for Clinical Use (SPCU)

In AU PS, SPCU is not **Must Support**. See the implementation guidance defined in the [Sex Parameter for Clinical Use (SPCU)](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html#sex-parameter-for-clinical-use-spcu) section of the AU Base [Sex and Gender](https://build.fhir.org/ig/hl7au/au-fhir-base/sexgender.html) page for more information.

