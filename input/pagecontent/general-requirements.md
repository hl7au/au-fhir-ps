### Conforming to AU Patient Summary

TBD

### Conformance Artifacts

#### AU PS Profiles and Extensions
The [Profiles and Extensions](profiles-and-extensions.html) page lists the AU PS profiles and extensions defined for this implementation guide. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the minimum elements, extensions, vocabularies and value sets that **SHALL** be present and constrains the way elements are used when conforming to the profile.

AU PS profile elements include mandatory and *Must Support* requirements. [Mandatory elements](#mandatory-elements) are required and have a minimum cardinality of 1 (min=1). [Must Support](#must-support-and-obligation) elements have defined conformance obligations in AU PS.

### Mandatory Elements
Mandatory elements are elements with minimum cardinality > 0. When an element is mandatory, the data is expected to always be present. Very rarely, it may not be, and in this circumstance the requirements defined by AU Core for [Missing Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-data) **SHALL** be applied. An element can be both *Must Support* and mandatory, in which case the requirements defined by AU Core for mandatory's Missing Data requirements apply as described in [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data).

The convention in this guide is to mark all mandatory elements as *Must Support* unless they are nested under an optional element.

### Must Support and Obligation
TBD


### Suppressed Data
In some circumstances, specific pieces of data may be hidden due to security or privacy reasons and in these circumstances the requirements defined by AU Core for [Suppressed Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#suppressed-data) **SHALL** be applied.