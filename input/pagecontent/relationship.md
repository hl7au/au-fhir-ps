This guide is built on top of the FHIR standard and, where available, [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/), [IPS](https://build.fhir.org/ig/HL7/fhir-ips), and [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/). It is compliant with the profile conformance requirements in [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core/) and [IPS](https://build.fhir.org/ig/HL7/fhir-ips/).


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
The primary intent of the [AUCDI](https://sparked.csiro.au/index.php/sparked-products-resources/aucdi/) is to design and govern a collection of coherent, reusable building blocks known as data groups. These data groups specify “what” the clinical requirements of the clinical information that should be included for data entry, data use, and sharing of information supporting healthcare delivery. However, it does not specify “how” the data is exchanged; this is the role fulfilled by the FHIR standard. AUCDI is not required to be implemented as a whole single product. Parts can be
implemented as required for specific use cases.

AUCDI R1 (published in June 2024) concentrated on identifying essential "core of the core" data elements; already present within most existing clinical systems. These data elements represented the absolute minimum data required to support standardised clinical information capture at the point of care and for safe and meaningful exchange of information to other care providers. AUCDI R2 builds upon R1, expanding on the initial "core", introducing additional data groups to support different use cases including "Patient summary".

AU Patient Summary is a technical specification that addresses constraints and obligations on data representation for exchange. AU Patient Summary enables system data to be mapped to an agreed FHIR format, produced, and consumed by systems in Australia.

See [AUCDI](aucdi.html) for the relationship between the "Patient summary" AUCDI data groups, elements, AU Core profiles, and AU Patient Summary profiles.

The relationship of AU Patient Summary to AUCDI and other implementation guides is shown in the figure below.

 <div> 
    <img src="context-colour.png" alt="Relationship to AUCDI and Other IGs" style="width:25%"/>
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


