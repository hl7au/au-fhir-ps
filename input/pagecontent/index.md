### Introduction
AU Patient Summary (AU PS) is provided to support the use of patient summaries in HL7® FHIR®© in an Australian context. AU PS is based on [IPS](https://hl7.org/fhir/uv/ips/STU2/index.html) and [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core), setting the minimum conformance expectations for implementing support for AU PS documents in systems.

AU PS is compliant with the requirements of IPS, e.g. AU PS data is conformant to IPS and systems that generate and consume AU PS documents are conformant to the requirements in IPS:
* A valid AU PS document IS a valid IPS document - the document instance validates against both IGs. 
* A conformant AU PS actor IS a conformant IPS actor - the conformance expectations for implementation for IPS are satisfied when implementing AU PS actor requirements.

For a detailed description of the requirements for implementing AU PS, see the [General Requirements](general-requirements.html#general-requirements) page.

A Patient Summary is:
* a health record extract comprising a core set of digital health and administrative data elements that provide a snapshot in time of a subject of care’s health information and healthcare.
* designed for supporting use case scenarios including planned and unplanned care, continuity of care and transition of care.

See [The AU PS](the-aups.html) for more information on the purpose, scope, context, and use of AU PS.

### Project Background

This implementation guide is under development through the [AU Patient Summary FHIR IG project](https://confluence.hl7.org/display/HAFWG/AU+Patient+Summary+FHIR+IG+Project) as part of the [Sparked AU FHIR Accelerator](https://sparked.csiro.au). The Sparked AU FHIR Accelerator is a community comprising government, technology vendors, provider organisations, peak bodies, practitioners, and domain experts, to accelerate the creation and use of national FHIR standards in health care information exchange.

The AU Patient Summary Sparked project includes:
- AUCDI - clinician focussed data requirements project.
- AU PS FHIR Implementation Guide - HL7 Australia technical data specification.

Additionally, a Patient Summary Clinical Focus Group (CFG), a sub-group of the Clinical Design Group, has developed a series of [consumer journeys](https://sparked.csiro.au/index.php/products-resources/au-ps-consumer-journeys/) that have been elaborated into a set of example use cases in this IG to provide guidance on how AU PS could be implemented.

<div> 
   <img src="AUPSTeamsContextb.png" alt="AU Patient Summary Development Context" style="width:75%"/>
  </div>
*Figure 1: AU PS development context*
<br/>

For more information on the relationship between AUCDI and AU PS, including mappings, see [AUCDI](aucdi.html).

### Dependencies
{% include dependency-table.xhtml %}
{% include expansion-params.xhtml %}

### How to Read This Guide

This guide is divided into several pages which are listed at the top of each page in the menu bar.

- [Home](index.html): This page provides the introduction and scope for this guide.
- [Conformance](conformance.html): These pages describe the set of rules to claim conformance to this guide including the expectations for *Must Support*  elements in AU PS profiles.
  - [General Requirements](general-requirements.html): This page defines requirements common to profiles used in this guide including the expectations for mandatory and *Must Support*  elements in AU PS profiles.
  - [Declaring Conformance](declaring-conformance.html): This page describes how to declare conformance to AU PS.
- [The AU PS](the-aups.html): This page describes the AU PS including structure, context of use, and localisation of the IPS.
- [Guidance](guidance.html): These pages list the guidance for this guide.
  - [General Guidance](general-guidance.html): This page provides guidance on using the profiles defined in this guide. 
  - [Generation and Access](generation-and-access.html): This page describes some options for generation and access of patient summary documents. 
  - [Sex and Gender](sex-and-gender.html): This page provides guidance on the representation of sex, gender, and related concepts.
  - [AUCDI](aucdi.html): This page maps AUCDI data groups and elements to FHIR artefacts in AU PS.
  - [Relationship With Other IGs](relationship.html): This page provides guidance on the relationship between AU PS, AUCDI, and other implementation guides.
  - [AU Variance Statement](variance.html): This page documents the variance from AU Base and AU Core.
  - [Comparison With Other National and International IGs](comparison.html): This page provides comparison between AU PS profiles and other national and international implementation guides.
  - [Future of AU PS](future.html): This page outlines the approach to developing AU PS.
- [Use Cases](usecase.html): These pages document a set of example use cases that assist in understanding how to implement AU PS.
   - [Interstate GP Visit](uc-interstate.html): This page documents the Interstate GP Visit - Patient Driven Patient Summary example use case.
   - [Referral to Specialist and Allied Health](uc-referral.html): This page documents the Referral to Specialist and Allied Health - Clinician Driven Patient Summary (as Supplemental Information) example use case.
- [Security and Privacy](security.html): This page documents the AU PS general security and privacy requirements and recommendations.
- [FHIR Artefacts](artefacts.html): These pages provide detailed descriptions and formal definitions for all the FHIR artefacts defined in this guide.
  - [Artefacts Summary](artifacts.html): This page lists the FHIR artefacts defined in this guide.
  - [Profiles and Extensions](profiles-and-extensions.html): This page describes the profiles and extensions that are defined in this guide to exchange data. Each profile page includes a narrative description and guidance, and formal definition. Guidance typically focuses on the profiled elements but can include guidance on un-profiled elements to aid with implementation.
  - [Terminology](terminology.html): This page lists the value sets and code systems supported in this guide.
  - [Actor Definitions](actors.html): This page defines the AU PS actors, AU PS Consumer and AU PS Producer.
- [Examples](examples.html): This page lists all the examples used in this guide.
- [Support](downloads.html): These pages provide supporting material for implementation of AU PS.
  - [Downloads](downloads.html): This page provides links to downloadable artefacts.
  - [License and Legal](license.html): This page outlines the license and legal requirements for material in AU PS.
- [Change Log](changes.html): This page documents the changes across versions of this guide.

### Collaboration
This guide is the product of collaborative work undertaken with participants from:

* [HL7 Australia AU Core Technical Design Group](https://confluence.hl7.org/display/HAFWG/HL7+Australia+-+AU+Core+Technical+Design+Group+Home)
* [HL7 Australia FHIR Working Group](https://confluence.hl7.org/display/HAFWG/HL7+Australia+FHIR+Work+Group+Home)
* Australian FHIR Implementers Community

Primary Editors: Brett Esler, Danielle Tavares-Rixon, Dusica Bojicic.