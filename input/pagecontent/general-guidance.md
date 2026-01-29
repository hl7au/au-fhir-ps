{::options toc_levels="1..4"/}

### Approach of this Implementation Guide
AU Patient Summary (AU PS) is provided to support the use of patient summaries in HL7® FHIR®© in an Australian context. AU PS is based on [IPS](https://hl7.org/fhir/uv/ips/STU2/index.html) and [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core), setting the minimum conformance expectations for implementing AU PS documents in systems.

AU PS, by design:
* ensures compliance with AU Core and IPS
* includes additional requirements agreed as necessary to support patient summaries in an Australian healthcare context (see [the AU PS](the-aups.html))
* supports varied stakeholder needs in the use of AU PS artefacts e.g. government policy, implementers, tooling developers, testers, IG authors/maintainers etc.

The approach to describing the 'minimum' in AU PS means modelling in such a way that 'at least' what is to be supported is defined without limiting meaningful options for business rules and different clinical workflows. AU PS artefacts are therefore modelled as open templates allowing for additional content including elements, extensions, resources, search parameters, operations, and terminology whilst ensuring the minimum requirements are met.

Australian realm IGs and implementers are expected to [comply with AU Base and AU Core](variance.html) and to define extensions, search parameters or operations (in order of precedence):
* in the FHIR standard (incl. FHIR Extensions Pack)
* in AU Base
* in a downstream IG (this IG)
* in a local IG only if necessary

#### Scope of AU PS FHIR Artefacts
AU PS profiles:
* [Resources](general-guidance.html#resource-profile-approach) to define minimum support expectations for use in the Australian healthcare context
* [Actors](general-guidance.html#actor-approach) to define systems that play a role in consuming and producing AU PS documents

In this release, AU PS does not define new extensions, search parameters, operations or [terminology](general-guidance.html#terminology-approach). AU PS does not include capability statements (the minimum capabilities (behaviours) to be supported for AU PS actors). Future releases of this IG may include capability statements, extensions, search parameters, operations, or terminology.

#### Extension Approach
AU PS does not define new extensions. All extensions included in AU PS are defined in the [FHIR Extensions Pack](https://hl7.org/fhir/extensions/) or [AU Base](http://build.fhir.org/ig/hl7au/au-fhir-base/profiles-and-extensions.html#extensions). A limited set of extensions are indicated as _Must Support_ in AU PS resource profiles; these supported extensions have been inherited from underlying AU Core profile.

It is anticipated that extension profiles may be included in future releases of this IG.

#### Terminology Approach
AU PS does not define new terminology FHIR artefacts (e.g. value sets or code systems). Terminology supported in AU PS are published in [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/terminology.html), the FHIR standard, [HL7 Terminology (THO)](https://terminology.hl7.org/), or the [National Clinical Terminology Service (NCTS)](https://www.healthterminologies.gov.au/). 

As part of profiling, AU PS inherits the AU Core localised terminology and indicates support expectations for an AU PS actor using _Must Support_ and Obligations. For more information on the terminology modelling inherited from AU Core see the guidance in AU Core [Use of Terminology Bindings](https://build.fhir.org/ig/hl7au/au-fhir-core/general-guidance.html#use-of-terminology-bindings). 

In terms of support in AU PS profiles, a coded element can have support defined for one or many value sets. Coded elements that define support for more than one value set include them in a profile by slicing the [Coding](http://hl7.org/fhir/R4/datatypes.html#Coding) part of the element and placing *Must Support* on each value set slice. These value set slices are not intended to prevent systems from supplying only a text value. Most coded *Must Support* elements in AU PS define support for one value set, which is bound to the supported element and no value set slice is present.

For:
* a list of the terminologies supported in AU PS, refer to the [Terminology](terminology.html) page. 
* a description of the localisation of terminology compared to the IPS, refer to [Terminology Localisation](the-aups.html#terminology-localisation)
* guidance on selection of terminology in HL7 AU IGs, refer to the AU Base guidance on [Terminology Selection](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#terminology-selection)

#### Resource Profile Approach

##### AU PS Profile Design Principles
 AU PS profiles are designed to ensure compliance with AU Core and IPS. AU PS profile design principles are as follows:
* AU PS profiles **SHALL** ensure resources validate against both IPS and AU Core profiles (where both profiles exist):
   - Cardinality
   - Fixed values and patterns
   - Data type sub-elements and profiles
   - Data type choices and references
   - Invariants
   - Must Support
   - Terminology bindings
* AU PS profiles **SHALL** validate reference elements against AU PS profiles (where defined), otherwise the AU Core profile where available, otherwise the IPS profile where available, otherwise the AU Base profile where available
* In AU PS profiles, inherited AU Core profile terminology bindings are preferenced over IPS profile terminology bindings:
   - where an element has a required binding, the element **SHALL** apply the intersection of both value sets (AU Core and IPS)
   - where an element has a lesser binding, use the AU Core value set and binding strength (where AU Core is equivalent or stronger) or use the IPS value set where the binding strength is stronger
* An AU PS profile **SHALL** inherit the IPS profile obligations and **MAY** strengthen the IPS profile obligations (using a specialisation of the defined obligation) or add an additional obligation (e.g. SHOULD:persist), as required for the Australian context. A weaker obligation **SHALL NOT** be specified.
* Where both AU Core and IPS profiles do not exist, **SHALL** ensure resources validate against:
   * IPS profile (where only the IPS profile exists)
   * AU Core profile (where only the AU Core profile exists)
* Where a profile referenced in AU PS Bundle is not defined in IPS, or has _Must Support_ elements with no obligations in IPS,  the AU PS obligations default to: 
  - AU PS Producer: SHALL:populate-if-known
  - AU PS Consumer: SHALL:handle and SHOULD:display 

Adopting the approach in both IPS and AU Core, AU PS profiles are 'open' and allow for additional content undefined by AU PS (and IPS) to be shared. See the section [Extensibility – 'Additional' Sections or Elements](general-guidance.html#extensibility--additional-sections-or-elements) for information. 

##### Profiling Approach

AU PS profiles:
* are derived from AU Core, where available, to inherit the nationally agreed localised terminology, identifiers, and extensions.
* are only constrained (e.g. cardinality, references, terminology, extensions) where the constraint is agreed to be a minimum requirement that is nationally relevant and applicable for all AU PS documents to avoid limiting options for downstream use case decisions and business rules. 
* elements and extensions that form the minimum requirements are labelled _Must Support_. 
* elements or extensions that are not labelled _Must Support_ are not part of the minimum requirements and are therefore not further constrained in AU PS.
  * an exception to this rule is inherited from underlying AU Core profiles that include an invariant to enforce that if a coded body site is provided, at least one coding is from SNOMED CT.
* are defined as open, allowing additional elements, extensions, and rules. This results in a more flexible template that can be used across wider contexts, but also means that the resource content is not closed, and applications have to decide how to handle content not described by the profile.

When modelling AU PS resource profiles, they:
* are derived from AU Core profiles, or where not available, the AU Base profile (where it exists)
* apply additional requirements inherited from IPS (in accordance with the [AU PS Profile Design Principles](general-guidance.html#au-ps-profile-design-principles)) 
* apply additional requirements agreed by the AU PS project, e.g. inclusion of AU PS Encounter profile 
* use compliesWithProfile to assert compliance with IPS

The differential view therefore shows the patient summary requirements that are additional to AU Core. In some profiles, e.g. [AU PS Organization](StructureDefinition-au-ps-organization.html), the only additional requirements from AU Core are the obligations for AU PS actors.

<div> 
    <img src="patient-profilingapproach.png" alt="AU PS Patient current profiling approach" style="width:40%"/>
  </div>
*Figure 1: Profiling approach for AU PS Patient profile*
<br/><br/>

The AU PS Bundle profile is not based on AU Core or AU Base as no resource profile exists in either IG. The approach to profiling for AU PS Bundle is to:
* apply requirements inherited from IPS (in accordance with the [AU PS Profile Design Principles](general-guidance.html#au-ps-profile-design-principles)) 
* apply additional requirements as agreed by the AU PS project
* use compliesWithProfile to assert compliance with IPS

<div> 
    <img src="psbundle-profilingapproach.png" alt="AU PS Bundle current profiling approach" style="width:40%"/>
  </div>
*Figure 2: Profiling approach for AU PS Bundle profile*
<br/><br/>

This approach to AU PS Bundle profiling has been taken as at this time there is a tooling limitation that prevents meeting both of the below conditions:
* derivation from Bundle (IPS)
* changing reference targets to AU PS profiles (as AU PS profiles derive from AU Core and not IPS they cannot be easily assessed as meeting IPS rules by the tooling)

Additional detail on profiling is:
* described in the guidance section [Localisation of the IPS](the-aups.html#localisation-of-the-ips)
* the modelling inherited from AU Core is described in the AU Core [Resource Profile Approach](https://build.fhir.org/ig/hl7au/au-fhir-core/general-guidance.html#resource-profile-approach)

###### Use of Must Support and Obligations
_[Must Support](general-requirements.html#must-support-and-obligation)_ is used to indicate the elements and extensions that form the minimum requirements of AU PS. Labelling an element _Must Support_ means that systems that produce or consume resources are to provide support for the element in some meaningful way. The FHIR standard does not define exactly what 'meaningful' support for an element means, but indicates that a profile needs to make clear exactly what kind of support is required when an element is labelled as _Must Support_.

The set of _Must Support_ elements in AU PS is inherited from AU Core and IPS resource profiles (i.e. the union of IPS and AU Core elements labelled *Must Support*). In addition, the mandatory elements in AU PS Bundle, are labelled with *Must Support* e.g. `Bundle.type`. This is applied as the convention in this guide is to mark all mandatory elements as *Must Support* unless they are nested under an optional element.

The meaning of _Must Support_ in AU PS is defined in:
* narrative in the IG (e.g. [Missing Data](general-requirements.html#missing-data) requirements)
* the [obligation extension](https://hl7.org/fhir/extensions/StructureDefinition-obligation.html) on each supported element in a profile, identifying the support expectations for AU PS actors
* narrative qualification of element obligations present in the profile specific implementation guidance

See [Must Support and Obligation](general-requirements.html#must-support-and-obligation) for a detailed description of how this is applied in AU PS. 

###### Potential Profiling Options

When managing [profile complexity and requirements](relationship.html) in the [national and international context for AU PS](the-aups.html#the-au-ps-au-patient-summary), the following mechanisms are available:
1. [Derived from Profiles (derive)](https://build.fhir.org/structuredefinition-definitions.html#StructureDefinition.baseDefinition)
1. Informal alignment (humans authoring of rules in a profile)
1. [Complies With Profile (compliesWithProfile)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-compliesWithProfile.html)
1. [Dependent Profiles (imposeProfile)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-imposeProfile.html)

These mechanisms offer differing capabilities and advantages. Typically HL7 AU profiles use derivation to manage compliance within HL7 AU inheritance. However, AU PS will comply to both HL7 AU (AU Core) and IPS and therefore additional mechanism(s) on top of derivation from the underlying HL7 AU profile stack are required. At this time additional requirements are included in AU PS profiles via informal alignment (i.e. human authoring, human checking, and compliesWithProfile checks).

<div class="stu-note" markdown="1">
For a human, the main differences with use of imposeProfile are:
- does not rely on humans to maintain compliance rules from the target profile
- does not visually show human reader of the source profile any rules from the target profile, i.e. a human reader must view and understand both profiles to understand the rules
- where two or more profiles offer optional alternatives (e.g. differing preferred bindings or data type choices) does not preference one over another

Currently the only AU PS profile to use imposeProfile is AU PS Composition . To support future maintenance it is under consideration that all AU PS profiles derive from AU Core, where available, and use imposeProfile to apply IPS rules. That would mean that a number of IPS-imposed requirements including cardinality, terminology, and flagging of <i>Must Support</i> would not be directly visible in the formal views within this guide. Or, if we chose to make the additional IPS constraints visible + use imposeProfile, those constraints would be repeated from a validation sense and could be an additional validation burden.

Users of this implementation guide are encouraged to provide their feedback about the potential use of imposeProfile.
</div><!-- stu-note -->

#### Actor Approach
AU PS actors are defined to describe the specific sets of functionality supported by systems that play a role in AU Core data exchange. Each actor is defined by:
* an actor definition that includes reference to support expectations (narrative conformance requirements)
* resource profiles that define expectations using _Must Support_ and Obligations 

In this release, AU PS does not include capability statement that describes the requirements for an AU PS actor. It is anticipated that capability statements may be included in future releases of this IG.

##### AU PS Actor Design Principles
 AU PS actors are designed to ensure compliance with IPS and support the [use of patient summaries in Australia](the-aups.html#aupintendedto). AU PS actor design principles are as follows:
* AU PS actor design to ensure compliance with AU Core and IPS:
  * **SHALL** inherit the narrative conformance requirements including Missing Data, Empty Sections, Known Absence of Data
  * **SHALL** inherit IPS Document requirements (see [AU PS Resource Profile Approach](general-guidance.html#resource-profile-approach))
  * **SHALL** inherit _Must Support_ and Obligation requirements
  * **MAY** strengthen inherited requirements as required for the Australian context. A weaker requirement **SHALL NOT** be specified.

### Extensibility – 'Additional' Sections or Elements
As in IPS, a producer can send:
- 'additional' elements beyond those flagged with *Must Support* in a profile
- 'additional' sections (often referred to as 'undefined' sections) beyond those defined in the AU PS Composition

Additional sections or elements are often required by other profiles the system may conform to, allowing local requirements, including technical and workflow context for the resource, to be reflected and extending the health information supported in exchanges. For this reason, extensibility is generally encouraged and expected in AU PS profiles. Only in some exceptionally rare use case profiles are rules tightened to limit the nature of additional information that can be sent. 

Implementers intending to populate the AU PS with an unprofiled resource type, e.g. MedicationAdministration, are recommended to consider the corresponding [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/) profile, e.g. [AU Base MedicationAdministration](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medicationadministration.html), as guidance for that resource type in an Australian healthcare context.


#### Extensibility – 'Additional' Sections
Implementers need to be aware, the rules of the `Composition.section:All Slices` defined in the AU PS Composition profile apply to all sections, defined or undefined:
- `Composition.section.title` is mandatory and has obligations defined for AU PS Producers and AU PS Consumers
- `Composition.section.text` is mandatory and has obligations defined for AU PS Producers and AU PS Consumers

It is recommended that where a producing system intends to populate 'additional' sections there is some definition available in a specification describing the intended contents and use of these additional sections. 

#### Extensibility – 'Additional' Elements
Specification authors adopting AU PS are encouraged to enable greater interoperability and software re-use by avoiding reductions in an element's cardinality.

Depending on local requirements, a consumer (i.e. client application) may ignore these 'additional' elements, may treat the data as for rendering only, or be capable of recognising and using the element. 

### Structuring Terminology Choices
The AU PS shares the same structure as IPS and contains sections that can include coded elements in reusable 'minimal' data blocks.

The AU PS identifies a number of [terminologies](terminology.html) as *Must Support* for AU PS consumers and producers. Primary terminologies used in this specification include [SNOMED CT Australian Edition (SNOMED CT-AU)](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#snomed-ct-australian-edition) for clinical concepts (e.g. allergies, problems, procedures, medicines), LOINC for observation codes (e.g. pathology results and vital signs), UCUM for units of measure,  ISO 3166 for countries, PBS Item codes for medicines, Australian Immunisation Register codes for vaccines, and FHIR defined CodeSystems.

Within [the AU PS](the-aups.html) context (i.e. the Australian healthcare context), the Australian localised value sets, developed and published by the [National Clinical Terminology Service](https://www.healthterminologies.gov.au) (NCTS) and the HL7 AU FHIR Working Group are preferred over IPS value sets to support the consumer on their healthcare journey in the AU healthcare context.

In an IPS context, IPS proposes that to support interoperability of IPS content between organisations that use different SNOMED CT value set content, a 'common proximal ancestor' strategy is used. See IPS [Structuring Terminology Choices](https://hl7.org/fhir/uv/ips/STU2/General-Principles.html#structuring-terminology-choices) for more information.
 

### Patient Safety in IPS Context
See the guidance defined in IPS [Patient Safety in IPS Context](https://hl7.org/fhir/uv/ips/STU2/General-Principles.html#patient-safety-in-ips-context).

### Medicinal Product Identification
See the guidance defined in AU Core [Medicine Information](https://build.fhir.org/ig/hl7au/au-fhir-core/medicine-information.html). 

### Representing Body Site, Which May Include Laterality
See the guidance defined in AU Core [Representing Body Site, Which May Include Laterality](https://build.fhir.org/ig/hl7au/au-fhir-core/general-guidance.html#representing-body-site-which-may-include-laterality). 

### Provenance
See the guidance defined in IPS [Provenance](https://hl7.org/fhir/uv/ips/STU2/Design-Conventions.html#provenance). 