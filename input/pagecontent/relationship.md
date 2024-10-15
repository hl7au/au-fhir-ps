This guide is built on top of the FHIR standard and, where available, [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/). It is compliant with the profile conformance requirements in [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/) and [IPS](https://build.fhir.org/ig/HL7/fhir-ips/).


The context of AU Patient Summary within the set of HL7 AU standards is shown in the figure below:
- the **FHIR standard** is the foundation, which creates a common platform or foundation on which a variety of different solutions are implemented. 
- **AU Base** defines local concepts for use in an Australian context introducing relevant identifiers, terminology, extensions. 
- **AU Core** defines a set of conformance requirements that enforce a set of 'minimum requirements' on the local concepts from AU Base, specifying the elements, extensions, vocabularies, and value sets that SHALL be present and how they SHALL be used, along with the RESTful API interactions.
- **Use case IGs** (AU eRequesting and AU Patient Summary) build on AU Core to address specific use cases, defining a set of conformance requirements on top of AU Core, using additional building blocks from AU Base as needed.

This layering of IGs balances relative adoption and implementation maturity of FHIR and requirements of the use cases involved.

  <div> 
    <img src="architecture.png" alt="Context of AU Patient Summary within the set of HL7 AU standards" style="width:65%"/>
  </div>
*Figure 2: Context of AU Patient Summary within the set of HL7 AU standards*
<br/>

### Relationship to AUCDI and other IGs
The primary intent of the [Australian Core Data for Interoperability (AUCDI)](https://sparked.csiro.au/index.php/sparked-products-resources/australian-core-data-for-interoperability/aucdi-release-1/) is to design and govern a collection of coherent, reusable building blocks known as ‘data groups’. These data groups specify “what” the clinical requirements of the clinical information that should be included for data entry, data use, and sharing of information supporting healthcare delivery. However, it does not specify “how” the data is exchanged; this is the role fulfilled by the FHIR standard. AUCDI is not required to be implemented as a whole single product. Parts can be implemented as required for specific use cases.

AUCDI is focused on an agreement of “the core of the core” common data elements; minimum data required to support standardised clinical information capture at the point of care as well as enable the safe and meaningful exchange of information to other care providers. AUCDI Release 2 (R2) will identify a set of core data groups and elements considered important for a minimal patient summary.

With AUCDI defining clinical data requirements, AU Core defining the minimum core digital health and administrative FHIR-based profiles, and AU Patient Summary providing detailed FHIR-based profiles for meeting patient summary requirements, an interpretation of AUCDI is necessary which is undertaken through the community.

Updates to AU Patient Summary depend upon community input and we encourage our audience to submit questions and feedback to AU Patient Summary specifications by clicking on the Propose a change link in the footer of every page. In addition, we encourage requesting any necessary clarifications to AUCDI through the <a href="https://sparked.csiro.au/index.php/sparked-products-resources/australian-core-data-for-interoperability/">AUCDI process</a> that helps inform future updates to AU Patient Summary.

See [AUCDI](aucdi.html) for the relationship between the AUCDI data groups, elements, AU Core profiles, and AU Patient Summary profiles.

The relationship of AU Patient Summary to AUCDI and other implementation guides is shown in the figure below.

 <div> 
    <img src="context-colour.png" alt="Relationship to AU Core and Other IGs" style="width:75%"/>
  </div>
*Figure 3: Relationship to AUCDI and Other IGs*
<br/>

Implementation Guide |Relationship
---|---
[AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/)|This IG defines Australian realm concepts including terminology, identifiers, and extensions. AU Patient Summary uses AU Base, where available, as the basis for profiles that define the FHIR resources to be supported, and the elements, extensions, vocabularies, and value sets that SHALL be present are identified, and how they are used is defined.
[AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/)|This IG defines a set of conformance requirements that enforce a set of 'minimum requirements' on the local concepts from AU Base, specifying the elements, extensions, vocabularies, and value sets that SHALL be present and how they SHALL be used, along with the RESTful API interactions. AU Patient Summary is compliant with AU Core, e.g. AU Core conformant data can be used to generate a patient summary that is conformant to AU Patient Summary and AU Patient Summary conformant data can be accessed by an AU Core conformant requester.
[HL7 Cross Paradigm Implementation Guide: Gender Harmony - Sex and Gender Representation](https://hl7.org/xprod/ig/uv/gender-harmony/informative1/)|This IG provides definitive guidance on how to exchange clinical sex and gender affirming information using HL7 models. Sex and gender concepts from this IG have been reviewed for the potential for adoption in Australia. Where adopted, these concepts are included by reference in AU Base and profiled in AU Core.
[International Patient Access](https://hl7.org/fhir/uv/ipa/STU1/)|This IG describes how an application acting on behalf of a patient can access information about the patient from a clinical records system using a FHIR based API. The REST API and profiles in this IG were reviewed and considered during development of AU Core and AU Patient Summary. AU Patient Summary is designed to be compatible with the RESTful data access in IPA, e.g. AU Patient Summary conformant data can be accessed by an IPA conformant client.
[International Patient Summary Implementation Guide](https://hl7.org/fhir/uv/ips/STU1.1/)|This IG describes specify how to represent in HL7 FHIR the International Patient Summary (IPS). An International Patient Summary (IPS) document is an electronic health record extract containing essential healthcare information about a subject of care. The profiles in this IG were reviewed and considered during development of AU Patient Summary. AU Patient Summary is compliant with IPS, e.g. AU Patient Summary data is conformant to IPS.
{:.grid}


