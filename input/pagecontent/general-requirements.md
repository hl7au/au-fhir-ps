{::options toc_levels="1..4"/}

### Conforming to AU Patient Summary

Systems claiming conformance to AU Patient Summary will represent digital health information using the content models of AU Patient Summary profiles AND implement the requirements for one or both [AU PS actors](actors.html).

The requirements of the FHIR standard and [FHIR Conformance Rules](http://hl7.org/fhir/conformance-rules.html) apply, and define the use of terms in this guide including the conformance verbs - **SHALL**, **SHALL NOT**, **SHOULD**, **SHOULD NOT**, **MAY**.

Implementers are advised to be familiar with the requirements of the FHIR standard and IPS when implementing AU PS, in particular:
- [IPS Generation and Data Inclusion](https://build.fhir.org/ig/HL7/fhir-ips/Generation-and-Data-Inclusion.html#generation-and-data-inclusion)
- [IPS Narrative and Language Translation](https://build.fhir.org/ig/HL7/fhir-ips/Design-Conventions.html#narrative-and-language-translation)
- [FHIR Terminology requirements](http://hl7.org/fhir/R4/terminologies.html)
- [FHIR Documents](https://hl7.org/fhir/R4/documents.html) 
- [FHIR RESTful API](http://hl7.org/fhir/R4/http.html) 
- [FHIR Search](http://hl7.org/fhir/R4/search.html)
- [FHIR Resource formats](http://hl7.org/fhir/R4/resource.html)
- [FHIR Data Types](http://hl7.org/fhir/R4/datatypes.html)

### Conformance Artifacts

#### AU PS Profiles and Extensions
The [Profiles and Extensions](profiles-and-extensions.html) page lists the AU PS profiles and extensions defined for this implementation guide. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the minimum elements, extensions, vocabularies and value sets that **SHALL** be present and constrains the way elements are used when conforming to the profile.

AU PS profile elements include mandatory and *Must Support* requirements. [Mandatory elements](#mandatory-elements) are required and have a minimum cardinality of 1 (min=1). [Must Support](#must-support-and-obligation) elements have defined conformance obligations in AU PS.

#### AU PS Actors
The [Actor Definitions](actors.html) page lists the AU PS actors defined for this implementation guide and the requirements for implementing that actor. An AU PS profile [StructureDefinition](http://hl7.org/fhir/R4/structuredefinition.html) defines the obligations for an AU PS actor when implementing that profile.

### Mandatory Elements
Mandatory elements are elements with minimum cardinality > 0. When an element is mandatory, the data is expected to always be present. Very rarely, it may not be, and in this circumstance the requirements defined by AU Core for [Missing Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-data) **SHALL** be applied. 

An element can be both *Must Support* and mandatory, in which case the requirements defined by AU Core for mandatory's Missing Data requirements **SHALL** be applied as described in [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data).

The convention in this guide is to mark all mandatory and conditionally mandatory elements as *Must Support* unless they are nested under an optional element.

### Missing Data and Empty Sections

There are situations when information is missing, this could be at the section level where a source system does not have information on a patient's medical devices, or may be at an element level within a resource. 

Where data is missing for an element within a resource and the reason is not known, systems **SHALL** implement the requirements of the [Missing Data](general-requirements.html#missing-data) section.

Where data is missing at the section level and the reason is not known, systems **SHALL** implement the requirements of the [Empty Sections](general-requirements.html#empty-sections) section.

Missing data is distinct from a known absence of data for either:
* no known x - where it is known, for example, that there are no known allergies for a patient
* workflow - where there is a known workflow reason information for the section is not available

#### Assertion statement of known absence of data
Where the source system can assert a known absence of data (No known X), the system **SHOULD** populate `Composition.section.entry` in accordance with the relevant profile specific implementation guidance for no known x. 

In AU PS this approach is preferred to using `Composition.section.emptyReason` due to the widely known and implemented patterns established within FHIR, and in AU Core, to assert known absence of clinical data.

For example, to represent that a patient does not have an allergy or category of allergies, an appropriate negation code (e.g. 716186003 \|No known allergy\| or 1003774007 \|No known Hevea brasiliensis latex allergy\|) is used in `AllergyIntolerance.code`.

#### Known absence of data due to workflow
Where the source system does not have information for a particular section and there is a known workflow reason, the system **SHALL** represent that reason by populating `Composition.section.emptyReason`:
* Prefer not to answer may be represented by sending the [Data Absent Reason](http://terminology.hl7.org/CodeSystem/data-absent-reason) code "asked-declined"
* Asked but not known may be represented by sending the [Data Absent Reason](http://terminology.hl7.org/CodeSystem/data-absent-reason) code "asked-unknown"
* Where the workflow does not support obtaining the information, it may be represented by sending the [List Empty Reason](https://hl7.org/fhir/R4/codesystem-list-empty-reason.html) code "notasked"

#### Missing Data

##### Missing Must Support and Optional Data

If the source system (producer) does not know the value for an optional element (minimum cardinality = 0), including elements labelled *Must Support*, as per the requirements defined in [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-optional-data), the data element **SHALL** be omitted from the resource.  

##### Missing Must Support and Mandatory Data

If the data element is a mandatory element (minimum cardinality is > 0), the element **SHALL** be present *even if* the source system (producer) does not know the value or the reason the value is absent. In this circumstance the requirements defined by AU Core for [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data) **SHALL** be applied:

#### Empty Sections

An AU PS Producer **SHOULD** omit non-mandatory sections when the source system does not have any information and does not know the reason the information is absent.

For a mandatory section (minimum cardinality is > 0), the section **SHALL** be present *even if* the source system does not have any information for that section or know the reason the information is absent. In this circumstance, an AU PS Producer **SHALL**:

* use the code `unavailable` from the [List Empty Reasons](http://terminology.hl7.org/CodeSystem/list-empty-reason) code system
* AU PS Consumers are advised that other meaningful values can be captured in `Composition.section.emptyReason` beyond missing or suppressed.
  
    Example: AU Patient Summary - Allergies and Intolerances Section where the patient's allergy information is not available.
    ~~~
        ...
        "section" : [
            {
                "title" : "Allergies and Intolerances",
                "code" : {
                "coding" : [
                    {
                    "system" : "http://loinc.org",
                    "code" : "48765-2",
                    "display" : "Allergies and adverse reactions Document"
                    }
                ]
                },
                "text" : {
                "status" : "generated",
                "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\" xml:lang=\"en-AU\" lang=\"en-AU\">There is no information available regarding the consumer's allergy conditions.</div>"
                },
                "emptyReason" : {
                "coding" : [
                    {
                    "system" : "http://terminology.hl7.org/CodeSystem/list-empty-reason",
                    "code" : "unavailable",
                    "display" : "Unavailable"
                    }
                ],
                "text" : "No information available"
                }
            },
        ...
    ~~~

### Suppressed Data
In some circumstances, specific pieces of data, are hidden due to security or privacy reasons:
* if an optional section, resource, or element (minimum cardinality = 0) is not able to be shared, it **SHALL** be omitted.
* if a mandatory section (minimum cardinality > 0) is not able to be shared use the code `unavailable` or `withheld` from the [List Empty Reason](https://hl7.org/fhir/R4/codesystem-list-empty-reason.html) in `Composition.section.emptyReason`.
* if a mandatory individual resource or element (minimum cardinality > 0) is not able to be shared use the code `unknown` or `masked` from the [DataAbsentReason Code System](http://terminology.hl7.org/CodeSystem/data-absent-reason) following the section on [Missing Data](#missing-data).

### Must Support and Obligation

<div class="stu-note" markdown="1">
This content has moved to master and is not replicated here: <a href="https://build.fhir.org/ig/hl7au/au-fhir-ps/branches/master/general-requirements.html#must-support-and-obligation">Must Support and Obligation</a> .
</div><!-- stu-note -->