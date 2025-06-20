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

The convention in this guide is to mark all mandatory elements as *Must Support* unless they are nested under an optional element.

### Must Support and Obligation
Labelling an element *[Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport)* means that systems that produce or consume resources **SHALL** provide support for the element in some meaningful way. The FHIR standard does not define exactly what 'meaningful' support for an element means, but indicates that a profile **SHALL** make clear exactly what kind of support is required when an element is labelled as *Must Support*.

In AU PS, the meaning of *Must Support* is specified in terms of [Obligation Codes](https://hl7.org/fhir/extensions/CodeSystem-obligation.html) in [obligation extensions](https://hl7.org/fhir/extensions/StructureDefinition-obligation.html) on the element definition. The obligation codes used to define the minimum obligations of *Must Support* elements in this implementation guide are reiterated below.

Actor | Code | Definition | Notes
--- | --- | --- | ---
[AU PS Consumer actor](ActorDefinition-au-ps-actor-consumer.html) | [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) | Conformant applications SHOULD display the value of this element when presenting the data from the resource to a human user |  This rule is vague in that doesn't specify any particular handling of the element. But it's important because an application that ignores this element is non-conformant. A good example would be a status code of 'entered-in-error' - how exactly a Resource Consumer handles this depends on the use case etc., but the application can never simply ignore such a status code. Note that whether the resource or information from it is stored for later use is irrelevant - when the resource or information in it is processed, the consequences of the element are considered.
| [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) | Conformant applications SHOULD display the value of this element when presenting the data from the resource to a human user. | Exactly how it is displayed is not specified, but it means that a human looking at the content of the resource is made aware of the value of the element so that they can consider the meaning of the resource.
[AU PS Producer actor](ActorDefinition-au-ps-actor-producer.html) |[SHALL:populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58populate)|Conformant applications producing resources SHALL include this element if a value is known and allowed to be shared| This implementation obligation means that whenever the producer knows the correct value for an element, it populates it. This is NOT the same as cardinality, as a 'populate' element can be omitted if no data exists or the data that exists is prohibited from being shared.
| [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58populate-if-known) | Conformant applications producing resources SHALL correctly populate this element if they know a value for the element, but it is acceptable if the system is unable to ever know a value for the element. | This obligation does not impose a requirement to be able to know a value, unlike populate and able-to-populate which do. 'Knowing' an element means that a value for the element is available in memory, persistent store, or is otherwise available within the system claiming conformance.
| [SHOULD:populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate)|Conformant applications producing resources SHOULD include this element if a value is known and allowed to be shared.| This implementation obligation means that whenever the producer knows the correct value for an element, it should populate it.
|  [MAY:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-MAY.58able-to-populate)| Conformant applications producing resources MAY be able to correctly populate this element. | Typically, this means that an application needs to demonstrate during some conformance testing process that there are some conditions under which it populates the element with a correct value. (i.e. not a data-absent-reason or equivalent.) 


*Must Support* elements are treated differently between [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html) and [AU PS Responder](ActorDefinition-au-ps-actor-responder.html) actors. *Must Support* on a profile element **SHALL** be interpreted as follows.

#### Presentation of Must Support and obligation in profiles
All elements with *Must Support* in AU PS are accompanied by an explicit obligation that identifies the expectations for one or more actors. When rendered in an implementation guide, each profile is presented in different formal views under tabs labelled "Differential Table", "Key Elements Table", and "Snapshot Table". Elements flagged with *Must Support* and stated obligations in these views are represented by <span style="padding-left: 3px; padding-right: 3px; color: white; background-color: red" title="This element must be supported">S</span><span style="padding-left: 3px; padding-right: 3px; color: white; background-color: red" title="This element has obligations">O</span> as shown below. 

 <div> 
    <img src="allergyintolerance-keyelementstable.png" alt="AU PS AllergyIntolerance Key Elements Table" style="width:100%"/>
  </div>
*Figure 1: Key Elements Table View*
<br/>

Implementers need to refer to the "Key Elements Table" to see the full set of elements that are mandatory or *Must Support* with obligations, and the full set of terminology requirements.  Implementers need to be aware that the full set of constraints (i.e. invariants) are only presented in the "Detailed Descriptions" tab or the raw representation (e.g. XML or JSON) of the profile.


#### Interpreting profile elements labelled Must Support
TBD

### Missing Data and Empty Sections

There are situations when information is missing, this could be at the section level where a source system does not have information on a patient's medical devices, or may be at an element level within a resource. 

Where data is missing for an element within a resource and the reason is not known, systems **SHALL** implement the requirements of the [Missing Data](general-requirements.html#missing-data) section.

Where data is missing at the section level and the reason is not known, systems **SHALL** implement the requiremens of the [Empty Section](general-requirements.html#empty-section) section.

Missing data is distinct from a known absence of data for either:
* no known x - where it is known, for example, that there are no known allergies for a patient
* workflow - where there is a known workflow reason the information is not available

#### No known x
Where the source system can assert a known absence of data (no known x), the system **SHOULD** populate `Composition.section.entry` in accordance with the relevant profile specific implementation guidance for no known x. 

This is in preference to population of `Composition.section.emptyReason` due to the widely known and implemented patterns established within FHIR generally to assert known absence.

For example, to represent that a patient does not have an allergy or category of allergies, an appropriate negation code (e.g. 716186003 |No known allergy| or 1003774007 |No known Hevea brasiliensis latex allergy|) is used in `AllergyIntolerance.code`.

#### Known absence of data due to workflow
Where the source system does not have information for a particular section and there is a known workflow reason, the system **MAY** represent that reason by populating `Composition.section.emptyReason`:
* Prefer not to answer may be represented by sending the [Data Absent Reason](http://terminology.hl7.org/CodeSystem/data-absent-reason) code "asked-declined"
* Asked but not known may be represented by sending the [Data Absent Reason](http://terminology.hl7.org/CodeSystem/data-absent-reason) code "asked-unknown"
* Not stated or inadequately described may be represented by sending the [List Empty Reason](https://hl7.org/fhir/R4/codesystem-list-empty-reason.html) code "unknown"
* Where the workflow does not support obtaining the information, it may be represented by sending the [List Empty Reason](https://hl7.org/fhir/R4/codesystem-list-empty-reason.html) code "notasked"

#### Missing Data

##### Missing Must Support and Optional Data

If the source system (producer) does not know the value for an optional element (minimum cardinality = 0), including elements labelled *Must Support*, as per the requirements defined in [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-optional-data), the data element **SHALL** be omitted from the resource.  

##### Missing Must Support and Mandatory Data

If the data element is a mandatory element (minimum cardinality is > 0), the element **SHALL** be present *even if* the source system (producer) does not know the value or the reason the value is absent. In this circumstance the requirements defined by AU Core for [Missing Must Support and Mandatory Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#missing-must-support-and-mandatory-data) **SHALL** be applied:

#### Empty Sections
If the section is a mandatory section (minimum cardinality is > 0), the section **SHALL** be present *even if* the source system does not have any information for that section or know the reason the information is absent.

For mandatory sections in AU PS Composition, an AU PS Producer:
* **SHALL** populate the `Composition.section.emptyReason` with a clinically relevant code when the section entry element is empty
* **MAY** populate the `Composition.section.entry` with a resource to assert known absence of data, e.g AllergyIntolerance with code representing ‘no known allergy’.

For mandatory sections in AU PS Composition, an AU PS Consumer:
* **SHALL** handle the section emptyReason when the entry element is empty

* **SHALL** handle a section entry with no known data coding (e.g. AllergyIntolerance.code: 716186003|No known allergy)
* **SHOULD** omit non-mandatory sections when the section does not have any information and does not know the reason is absent

### Suppressed Data
In some circumstances, specific pieces of data may be hidden due to security or privacy reasons and in these circumstances the requirements defined by AU Core for [Suppressed Data](https://build.fhir.org/ig/hl7au/au-fhir-core/general-requirements.html#suppressed-data) **SHALL** be applied:
* requirements of AU Core Responder apply to AU Patient Summary Producer
* requirements of AU Core Requester apply to AU Patient Summary Consumer