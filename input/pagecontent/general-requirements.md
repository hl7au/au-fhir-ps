### Conforming to AU Patient Summary

TBD.

The requirements of the FHIR standard and [FHIR Conformance Rules](http://hl7.org/fhir/conformance-rules.html) apply, and define the use of terms in this guide including the conformance verbs - **SHALL**, **SHALL NOT**, **SHOULD**, **SHOULD NOT**, **MAY**.

Implementers are advised to be familiar with the requirements of the FHIR standard and IPS when implementing AU PS, in particular:
- [IPS Generation and Data Inclusion](https://build.fhir.org/ig/HL7/fhir-ips/Generation-and-Data-Inclusion.html#generation-and-data-inclusion)
- [IPS Narrative and Language Translation](https://build.fhir.org/ig/HL7/fhir-ips/Design-Conventions.html#narrative-and-language-translation)
- [FHIR Terminology requirements](http://hl7.org/fhir/R4/terminologies.html)
- [FHIR RESTful API](http://hl7.org/fhir/R4/http.html) 
- [FHIR Search](http://hl7.org/fhir/R4/search.html)
- [FHIR Resource formats](http://hl7.org/fhir/R4/resource.html)
- [FHIR Data Types](http://hl7.org/fhir/R4/datatypes.html)

### Conformance Artifacts

#### AU PS Profiles and Extensions
The [Profiles and Extensions](profiles-and-extensions.html) page lists the AU PS profiles and extensions defined for this implementation guide. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the minimum elements, extensions, vocabularies and value sets that **SHALL** be present and constrains the way elements are used when conforming to the profile.

AU PS profile elements include mandatory and *Must Support* requirements. [Mandatory elements](#mandatory-elements) are required and have a minimum cardinality of 1 (min=1). [Must Support](#must-support-and-obligation) elements have defined conformance obligations in AU PS.

### Mandatory Elements
Mandatory elements are elements with minimum cardinality > 0. When an element is mandatory, the data is expected to always be present. Very rarely, it may not be, and in this circumstance the requirements defined by AU Core for [Missing Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-data) **SHALL** be applied. 

An element can be both *Must Support* and mandatory, in which case the requirements defined by AU Core for mandatory's Missing Data requirements **SHALL** be applied as described in [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data).

The convention in this guide is to mark all mandatory elements as *Must Support* unless they are nested under an optional element.

### Must Support and Obligation
Labelling an element *[Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport)* means that systems that produce or consume resources **SHALL** provide support for the element in some meaningful way. The FHIR standard does not define exactly what 'meaningful' support for an element means, but indicates that a profile **SHALL** make clear exactly what kind of support is required when an element is labelled as *Must Support*.

TBD - to add defined and agreed actors.

#### Presentation of Must Support and obligation in profiles
TBD

#### Interpreting profile elements labelled Must Support
TBD

### Missing Data

There are situations when information for a particular data element is missing and the source system does not know the reason for the absence of data. 

#### Missing Must Support and Optional Data

If the source system does not know the value for an optional element (minimum cardinality = 0), including elements labelled *Must Support*, as per the requirements defined in [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-optional-data) the data element **SHALL** be omitted from the resource.  

#### Missing Must Support and Mandatory Data

If the data element is a mandatory element (minimum cardinality is > 0), the element **SHALL** be present *even if* the source system does not know the value or the reason the value is absent. The requirements for the requirements defined by AU Core for [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data) **SHALL** be applied.

### Suppressed Data
In some circumstances, specific pieces of data may be hidden due to security or privacy reasons and in these circumstances the requirements defined by AU Core for [Suppressed Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#suppressed-data) **SHALL** be applied.