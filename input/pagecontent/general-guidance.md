{::options toc_levels="1..4"/}

### Profiling Approach
AU PS profiles will by design:
* ensure resource compliance with AU Core and IPS
* support additional requirements agreed as necessary to support patient summaries in an Australian healthcare context
* support varied stakeholder needs and use of AU Patient Summary artefacts e.g. government policy, implementers, tooling developers, testers, IG authors/maintainers etc.

AU PS profiles:
* are based on the AU Core profile (where it exists) 
* have additional requirements inherited from IPS applied (as determined by the [AU PS Profile Design Principles](general-guidance.html#au-ps-profile-design-principles)) 
* have additional requirements as agreed by this project applied
* use compliesWithProfile to assert compliance with IPS

The differential view therefore shows the patient summary requirements that are additional to AU Core. In some profiles, e.g. [AU PS Organization](StructureDefinition-au-ps-organization.html), there are no requirements additional to AU Core.

<div> 
    <img src="aupspatient-profilingapproach.png" alt="AU Patient Summary Patient current profiling approach" style="width:40%"/>
  </div>
*Figure 1: Profiling approach for AU PS Patient profile*
<br/><br/>

<div class="stu-note" markdown="1">
AU PS is undertaking a series of profile walkthroughs with the community, and to support that activity some profiles do not yet have this approach applied. Instead rules from AU Core and IPS are applied via human authoring. This is to support the human-centric design discussions early in the AU Patient Summary project. Post the walkthrough of each profile, it is converted to the target approach, and any additional local requirements identified during that walkthrough are applied.
</div><!-- stu-note -->


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

#### Profiling Options

When managing profile complexity and requirements in the [national and international context for AU Patient Summary](relationship.html#relationship-to-aucdi-and-other-igs), the following mechanisms are available:
1. [Derived from Profiles (derive)](https://build.fhir.org/structuredefinition-definitions.html#StructureDefinition.baseDefinition)
1. Informal alignment (humans authoring rules in a profile)
1. [Complies With Profile (compliesWith)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-compliesWithProfile.html)
1. [Dependent Profiles (imposeProfile)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-imposeProfile.html)

These mechanisms offer differing capabilities and advantages. Typically HL7 AU profiles have used derivation to manage compliance within HL7 AU inheritance. However, AU Patient Summary will comply to both HL7 AU (AU Core) and IPS and therefore additional mechanism(s) on top of derivation from the base HL7 AU profile are required. At this time additional requirements are included in profiles via informal alignment.

<div class="stu-note" markdown="1">
For a human, the main differences with use of imposeProfile are:
- does not rely on humans to maintain compliance rules from the target profile
- does not visually show human reader of the source profile any rules from the target profile, i.e. a human reader must view and understand both profiles to understand the rules
- where two or more profiles offer optional alternatives (e.g. differing preferred bindings or data type choices) does not in the profile preference one over another

Currently no AU Patient Summary profile uses imposeProfile. To support future maintenance it is under consideration that all AU Patient Summary profiles derive from AU Core, where available, and use imposeProfile to apply IPS rules. That would mean that a number of IPS-imposed requirements including cardinality, terminology, and flagging of <i>Must Support</i> would not be directly visible in the formal views within this guide. Or, if we chose to make the additional IPS constraints visible + use imposeProfile, those constraints would be repeated from a validation sense and be an additional validation burden.

Users of this implementation guide are encouraged to provide their feedback about the potential use of imposeProfile.
</div><!-- stu-note -->
