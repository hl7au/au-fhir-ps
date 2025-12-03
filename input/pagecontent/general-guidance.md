### Profiling Approach
AU PS profiles will by design:
* ensure resource compliance with AU Core and IPS
* support additional requirements agreed as necessary to support patient summaries in an Australian healthcare context
* support varied stakeholder needs and use of AU PS artefacts e.g. government policy, implementers, tooling developers, testers, IG authors/maintainers etc.

AU PS profiles:
* are based on the AU Core profile, or where not available, the AU Base profile (where it exists)
* apply additional requirements inherited from IPS (as determined by the [AU PS Profile Design Principles](general-guidance.html#au-ps-profile-design-principles)) 
* have additional requirements as agreed by the AU PS project applied
* use compliesWithProfile to assert compliance with IPS

The differential view therefore shows the patient summary requirements that are additional to AU Core. In some profiles, e.g. [AU PS Organization](StructureDefinition-au-ps-organization.html), the only additional requirements from AU Core are the obligations for AU PS actors.

<div> 
    <img src="aupspatient-profilingapproach.png" alt="AU PS Patient current profiling approach" style="width:40%"/>
  </div>
*Figure 1: Profiling approach for AU PS Patient profile*
<br/><br/>

The AU PS Bundle profile is not based on AU Core or AU Base (no resource profile exists). The approach to profiling for AU PS Bundle is to:
* apply requirements inherited from IPS (as determined by the [AU PS Profile Design Principles](general-guidance.html#au-ps-profile-design-principles)) 
* apply additional requirements as agreed by the AU PS project
* use compliesWithProfile to assert compliance with IPS

This approach to AU PS Bundle profiling has been taken as at this time there is a tooling limitation that prevents meeting both of the below conditions:
* derivation from Bundle (IPS)
* changing reference targets to AU PS profiles (as AU PS profiles derive from AU Core and not IPS they cannot be easily assessed as meeting IPS rules by the tooling)

#### AU PS Profile Design Principles

 AU PS profile design to ensure compliance with AU Core and IPS is agreed to as follows. AU PS profiles:
* **SHALL** ensure resources validate against both IPS and AU Core profiles (where both profiles exist)
   - Cardinality
   - *Must Support*
   - Fixed values and patterns
   - Data type sub-elements and profiles
   - Data type choices
   - Invariants
* Where both AU Core and IPS profiles do not exist, **SHALL** ensure resources validate against:
   * IPS profile (where only the IPS profile exists)
   * AU Core profile (where only the AU Core profile exists)
* AU PS profiles **SHALL** validate reference elements against AU PS profile where defined
* In AU PS profiles, inherited AU Core profile value sets are preferred over equivalent IPS profile value sets:
   - where an element has a required binding, the element **SHALL** apply the intersection of both value sets (AU Core and IPS)
   - where an element has a lesser binding, use the AU Core value set and binding strength (where AU Core is equivalent or stronger) or use the IPS value set where the binding strength is stronger

Adopting the approach in both IPS and AU Core, AU PS profiles are 'open' and allow for additional content undefined by AU PS (and IPS) to be shared. See the section [Extensibility – “Additional” Sections or Elements](general-guidance.html#extensibility--additional-sections-or-elements) for information. 

#### Profiling Options

When managing [profile complexity and requirements](relationship.html) in the [national and international context for AU PS](the-aups.html#the-au-ps-au-patient-summary), the following mechanisms are available:
1. [Derived from Profiles (derive)](https://build.fhir.org/structuredefinition-definitions.html#StructureDefinition.baseDefinition)
1. Informal alignment (humans authoring of rules in a profile)
1. [Complies With Profile (compliesWith)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-compliesWithProfile.html)
1. [Dependent Profiles (imposeProfile)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-imposeProfile.html)

These mechanisms offer differing capabilities and advantages. Typically HL7 AU profiles use derivation to manage compliance within HL7 AU inheritance. However, AU PS will comply to both HL7 AU (AU Core) and IPS and therefore additional mechanism(s) on top of derivation from the underlying HL7 AU profile stack are required. At this time additional requirements are included in AU PS profiles via informal alignment (i.e. human authoring, human checking, and compliesWith checks).

<div class="stu-note" markdown="1">
For a human, the main differences with use of imposeProfile are:
- does not rely on humans to maintain compliance rules from the target profile
- does not visually show human reader of the source profile any rules from the target profile, i.e. a human reader must view and understand both profiles to understand the rules
- where two or more profiles offer optional alternatives (e.g. differing preferred bindings or data type choices) does not preference one over another

Currently no AU PS profile uses imposeProfile. To support future maintenance it is under consideration that all AU PS profiles derive from AU Core, where available, and use imposeProfile to apply IPS rules. That would mean that a number of IPS-imposed requirements including cardinality, terminology, and flagging of <i>Must Support</i> would not be directly visible in the formal views within this guide. Or, if we chose to make the additional IPS constraints visible + use imposeProfile, those constraints would be repeated from a validation sense and could be an additional validation burden.

Users of this implementation guide are encouraged to provide their feedback about the potential use of imposeProfile.
</div><!-- stu-note -->

### Extensibility – “Additional” Sections or Elements
As in IPS, a producer can send:
- "additional" elements beyond those flagged with *Must Support* in a profile
- "additional" sections (often referred to as "undefined" sections) beyond those defined in the AU PS Composition

Additional sections or elements are often required by other profiles the system may conform to, allowing local requirements, including technical and workflow context for the resource, to be reflected and extending the health information supported in exchanges. For this reason, extensibility is generally encouraged and expected in AU PS profiles. Only in some exceptionally rare use case profiles are rules tightened to limit the nature of additional information that can be sent. 

Implementers intending to populate the AU PS with an unprofiled resoure type, e.g. MedicationAdministration, are recommended to consider the corresponding [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/) profile, e.g. [AU Base MedicationAdministration](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medicationadministration.html), as guidance for that resource type in an Australian healthcare context.


#### Extensibility – “Additional” Sections
Implementers need to be aware, the rules of the `Composition.section:All Slices` defined in the AU PS Composition profile apply to all sections, defined or undefined:
- `Composition.section.title` is mandatory and has obligations defined for AU PS Producers and AU PS Consumers
- `Composition.section.text` is mandatory and has obligations defined for AU PS Producers and AU PS Consumers

It is recommended that where a producing system intends to populate "additional" sections there is some definition available in a specification describing the intended contents and use of these additional sections. 

#### Extensibility – “Additional” Elements
Specification authors adopting AU PS are encouraged to enable greater interoperability and software re-use by avoiding reductions in an element's cardinality.

Depending on local requirements, a consumer (i.e. client application) may ignore these "additional" elements, may treat the data as for rendering only, or be capable of recognising and using the element. 

### Structuring Terminology Choices
The AU PS shares the same structure as IPS and contains sections that can include coded elements in reusable “minimal” data blocks.

The AU PS identifies a number of [terminologies](terminology.html) as *Must Support* for AU PS consumers and producers. Primary terminologies used in this specification include [SNOMED CT Australian Edition (SNOMED CT-AU)](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#snomed-ct-australian-edition) for clinical concepts (e.g. allergies, problems, procedures, medicines), LOINC for observation codes (e.g. pathology results and vital signs), UCUM for units of measure,  ISO 3166 for countries, PBS Item codes for medicines, Australian Immunisation Register codes for vaccines, and FHIR defined CodeSystems.

Within [the AU PS](the-aups.html) context (i.e. the Australian healthcare context), the Australian localised value sets, developed and published by the [National Clinical Terminology Service](https://www.healthterminologies.gov.au) (NCTS) and the HL7 AU FHIR Working Group are preferred over IPS value sets to support the consumer on their healthcare journey in the AU healthcare context.

In an IPS context, IPS proposes that to support interoperability of IPS content between organisations that use different SNOMED CT value set content, a "common proximal ancestor" strategy is used. See IPS [Structuring Terminology Choices](https://hl7.org/fhir/uv/ips/STU2/General-Principles.html#structuring-terminology-choices) for more information.
 

### Patient Safety in IPS Context
See the guidance defined in IPS [Patient Safety in IPS Context](https://hl7.org/fhir/uv/ips/STU2/General-Principles.html#patient-safety-in-ips-context).

### Medicinal Product Identification
See the guidance defined in AU Core [Medicine Information](https://build.fhir.org/ig/hl7au/au-fhir-core/medicine-information.html). 

### Representing Body Site, Which May Include Laterality
See the guidance defined in AU Core [Representing Body Site, Which May Include Laterality](https://build.fhir.org/ig/hl7au/au-fhir-core/general-guidance.html#representing-body-site-which-may-include-laterality). 

### Provenance
See the guidance defined in IPS [Provenance](https://hl7.org/fhir/uv/ips/STU2/Design-Conventions.html#provenance). 