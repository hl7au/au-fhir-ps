### Profiling Approach
AU PS profiles will by design:
* ensure compliance with AU Core and IPS
* support additional requirements agreed as necessary to support patient summaries in an Australian healthcare context
* support varied stakeholder needs and use of AU Patient Summary artefacts e.g. government policy, implementers, tooling developers, testers, IG authors/maintainers etc.

 Profile compliance with AU Core and IPS is agreed to as:
* **SHALL** validate against both IPS and AU Core profiles when both profiles defined
   - Cardinality
   - *Must Support*
   - Fixed values and patterns
   - Data type sub-elements and profiles
   - Data type choices
   - Invariants
* **SHALL** validate reference elements against AU PS profile where defined
* AU Core profile value sets are preferred over IPS profile value sets :
   - where an element has a required binding, the element **SHALL** apply the intersection of both value sets (AU Core and IPS)
   - where an element has a lesser binding, use the AU Core value set and binding strength (where AU Core is equivalent or stronger) or use the IPS value set where the binding strength is stronger

When managing profile complexity and requirements in the [national and international context for AU Patient Summary](file:///C:/work/git/au-fhir-ps/output/relationship.html#relationship-to-aucdi-and-other-igs), FHIR offers the following mechanisms:
1. [Derived from Profiles (derive)](https://build.fhir.org/structuredefinition-definitions.html#StructureDefinition.baseDefinition)
1. Informal alignment (humans authoring rules in a profile)
1. [Complies With Profile (compliesWith)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-compliesWithProfile.html)
1. [Dependent Profiles (imposeProfile)](https://hl7.org/fhir/extensions/StructureDefinition-structuredefinition-imposeProfile.html)

These mechanisms offer differing capabilities and advantages. Typically HL7 AU profiles have used derivation to manage compliance within HL7 AU inheritence. However, AU Patient Summary will comply to both HL7 AU (AU Core) and IPS and therefore additional mechanism(s) are required.

<div class="stu-note" markdown="1">
For a human, the main differences with use of imposeProfile are:
- does not rely on humans to maintain compliance rules from the target profile
- does not visually show human reader of the source profile any rules from the target profile, i.e. a human reader must view and understand both profiles to understand the rules

While only AU Patient Summary Composition currently uses imposeProfile, to support future maintenance it is under consideration that all AU Patient Summary profiles derive from AU Core, where available, and use imposeProfile to apply IPS rules. That would mean that a number of IPS-imposed requirements including cardinality, terminology, and flagging of Must Support would not be directly visible in the formal views within this guide.

Users of this implementation guide are encouraged to provide their feedback about the potential use of imposePrile.
</div><!-- stu-note -->



AU Patient Summary Composition currently:
* derives from AU Base
* apply agreed requirements for AU Patient Summary from community discussions (human authors)
* use imposeProfile to enforce IPS constraints

*Note: Rules from IPS are applied via use of imposeProfile*

<div> 
    <img src="aupscomp-current.png" alt="AU Patient Summary Composition current profiling approach" style="width:55%"/>
  </div>
*Figure 1: AU Patient Summary Composition current profiling approach*
<br/><br/>

All other profiles currently :
* derives from AU Base, where available
* apply AU Core and IPS requirements (human authors)
* use compliesWith to assert compliance with IPS

*Note: Rules from AU Core and IPS are applied via human authoring. This has been undertaken in support of human-centric design discussions early in the AU Patient Summary project.*

TBD
