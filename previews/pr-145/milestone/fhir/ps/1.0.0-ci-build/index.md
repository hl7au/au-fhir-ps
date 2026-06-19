# Home - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* **Home**

## Home

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org.au/fhir/ps/ImplementationGuide/hl7.fhir.au.ps | *Version*:1.0.0-ci-build | |
| * IG Standards status: *[Draft](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels): 1 | *Computable Name*:AUPatientSummaryImplementationGuide |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved. | | |

### Introduction

AU Patient Summary (AU PS) is provided to support the use of patient summaries in HL7® FHIR®© in an Australian context. AU PS is based on [IPS](https://hl7.org/fhir/uv/ips/STU2/index.html) and [AU Core](https://build.fhir.org/ig/hl7au/au-fhir-core), setting the minimum conformance expectations for implementing support for AU PS documents in systems.

AU PS is compliant with the requirements of IPS, e.g. AU PS data is conformant to IPS and systems that generate and consume AU PS documents are conformant to the requirements in IPS:

* A valid AU PS document IS a valid IPS document - the document instance validates against both IGs.
* A conformant AU PS actor IS a conformant IPS actor - the conformance expectations for implementation for IPS are satisfied when implementing AU PS actor requirements.

For a detailed description of the requirements for implementing AU PS, see the [General Requirements](general-requirements.md#general-requirements) page.

A Patient Summary is:

* a health record extract comprising a core set of digital health and administrative data elements that provide a snapshot in time of a subject of care’s health information and healthcare.
* designed for supporting use case scenarios including planned and unplanned care, continuity of care and transition of care.

See [The AU PS](the-aups.md) for more information on the purpose, scope, context, and use of AU PS.

### Project Background

This implementation guide is under development through the [AU Patient Summary FHIR IG project](https://confluence.hl7.org/spaces/HAAUCOREWG/pages/281216147/AU+Patient+Summary+FHIR+IG+Project) as part of the [Sparked AU FHIR Accelerator](https://sparked.csiro.au). The Sparked AU FHIR Accelerator is a community comprising government, technology vendors, provider organisations, peak bodies, practitioners, and domain experts, to accelerate the creation and use of national FHIR standards in health care information exchange.

The AU Patient Summary Sparked project includes:

* Australian Clinical Data for Interoperability (AUCDI) - clinician focussed data requirements project.
* AU PS FHIR Implementation Guide - HL7 Australia technical data specification.

Additionally, a Patient Summary Clinical Focus Group (CFG), a sub-group of the Clinical Design Group, has developed a series of [consumer journeys](https://sparked.csiro.au/index.php/products-resources/au-ps-consumer-journeys/) that have been elaborated into a set of example use cases in this IG to provide guidance on how AU PS could be implemented.

**Figure 1: AU PS development context** 

For more information on the relationship between AUCDI and AU PS, including mappings, see [AUCDI](aucdi.md).

### Dependencies








* Parameter: system-version
  * Value: SNOMED CT[AU]

### How to Read This Guide

This guide is divided into several pages which are listed at the top of each page in the menu bar.

* [Home](index.md): This page provides the introduction and scope for this guide.
* [Conformance](conformance.md): These pages describe the set of rules to claim conformance to this guide including the expectations for **Must Support** elements in AU PS profiles. 
* [General Requirements](general-requirements.md): This page defines requirements common to profiles used in this guide including the expectations for mandatory and **Must Support** elements in AU PS profiles.
* [Declaring Conformance](declaring-conformance.md): This page describes how to declare conformance to AU PS.
 
* [The AU PS](the-aups.md): This page describes the AU PS including structure, context of use, and localisation of the IPS.
* [Guidance](guidance.md): These pages list the guidance for this guide. 
* [General Guidance](general-guidance.md): This page provides guidance on using the profiles defined in this guide.
* [Generation and Access](generation-and-access.md): This page describes some options for generation and access of patient summary documents.
* [Sex and Gender](sex-and-gender.md): This page provides guidance on the representation of sex, gender, and related concepts.
* [AUCDI](aucdi.md): This page maps AUCDI data groups and elements to FHIR artefacts in AU PS.
* [Relationship With Other IGs](relationship.md): This page provides guidance on the relationship between AU PS, AUCDI, and other implementation guides.
* [AU Variance Statement](variance.md): This page documents the variance from AU Base and AU Core.
* [Comparison With Other National and International IGs](comparison.md): This page provides comparison between AU PS profiles and other national and international implementation guides.
* [Future of AU PS](future.md): This page outlines the approach to developing AU PS.
 
* [Use Cases](usecase.md): These pages document a set of example use cases that assist in understanding how to implement AU PS. 
* [Interstate GP Visit](uc-interstate.md): This page documents the Interstate GP Visit - Patient Driven Patient Summary example use case.
* [Referral to Specialist and Allied Health](uc-referral.md): This page documents the Referral to Specialist and Allied Health - Clinician Driven Patient Summary (as Supplemental Information) example use case.
 
* [Security and Privacy](security.md): This page documents the AU PS general security and privacy requirements and recommendations.
* [FHIR Artefacts](artefacts.md): These pages provide detailed descriptions and formal definitions for all the FHIR artefacts defined in this guide. 
* [Artefacts Summary](artifacts.md): This page lists the FHIR artefacts defined in this guide.
* [Profiles and Extensions](profiles-and-extensions.md): This page describes the profiles and extensions that are defined in this guide to exchange data. Each profile page includes a narrative description and guidance, and formal definition. Guidance typically focuses on the profiled elements but can include guidance on un-profiled elements to aid with implementation.
* [Terminology](terminology.md): This page lists the value sets and code systems supported in this guide.
* [Actor Definitions](actors.md): This page defines the AU PS actors, AU PS Consumer and AU PS Producer.
 
* [Examples](examples.md): This page lists all the examples used in this guide.
* [Support](support.md): These pages provide supporting material for implementation of AU PS. 
* [Downloads](downloads.md): This page provides links to downloadable artefacts.
* [License and Legal](license.md): This page outlines the license and legal requirements for material in AU PS.
 
* [Change Log](changes.md): This page documents the changes across versions of this guide.

### Collaboration

This guide is the product of collaborative work undertaken with participants from:

* [HL7 Australia AU Core Work Group](https://confluence.hl7.org/spaces/HAAUCOREWG/pages/184913442/HL7+Australia+-+AU+Core+Work+Group+Home)
* [HL7 Australia FHIR Working Group](https://confluence.hl7.org/display/HAFWG/HL7+Australia+FHIR+Work+Group+Home)
* Australian FHIR Implementers Community

Primary Editors: Brett Esler, Danielle Tavares-Rixon, Dusica Bojicic.



## Resource Content

```json
{
  "resourceType" : "ImplementationGuide",
  "id" : "hl7.fhir.au.ps",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
    "valueCode" : "draft"
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 1
  }],
  "url" : "http://hl7.org.au/fhir/ps/ImplementationGuide/hl7.fhir.au.ps",
  "version" : "1.0.0-ci-build",
  "name" : "AUPatientSummaryImplementationGuide",
  "title" : "AU Patient Summary Implementation Guide",
  "status" : "active",
  "experimental" : false,
  "date" : "2026-06-19T08:07:30+00:00",
  "publisher" : "HL7 Australia",
  "contact" : [{
    "name" : "HL7 Australia FHIR Work Group",
    "telecom" : [{
      "system" : "url",
      "value" : "https://confluence.hl7.org/display/HAFWG",
      "use" : "work"
    }]
  }],
  "description" : "AU Patient Summary (AU PS) is provided to support the use of patient summaries in HL7® FHIR®© in an Australian context. It complies with the requirements defined in IPS and AU Core, and sets the minimum expectations on FHIR resources to support conformance and implementation in systems.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "AU"
    }]
  }],
  "copyright" : "Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved.",
  "packageId" : "hl7.fhir.au.ps",
  "license" : "CC0-1.0",
  "fhirVersion" : ["4.0.1"],
  "dependsOn" : [{
    "id" : "hl7tx",
    "extension" : [{
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/implementationguide-dependency-comment",
      "valueMarkdown" : "Automatically added as a dependency - all IGs depend on HL7 Terminology"
    }],
    "uri" : "http://terminology.hl7.org/ImplementationGuide/hl7.terminology",
    "packageId" : "hl7.terminology.r4",
    "version" : "7.2.0"
  },
  {
    "id" : "hl7ext",
    "extension" : [{
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/implementationguide-dependency-comment",
      "valueMarkdown" : "Automatically added as a dependency - all IGs depend on the HL7 Extension Pack"
    }],
    "uri" : "http://hl7.org/fhir/extensions/ImplementationGuide/hl7.fhir.uv.extensions",
    "packageId" : "hl7.fhir.uv.extensions.r4",
    "version" : "5.3.0"
  },
  {
    "uri" : "http://hl7.org/fhir/uv/ips/ImplementationGuide/hl7.fhir.uv.ips",
    "packageId" : "hl7.fhir.uv.ips",
    "version" : "2.0.0"
  },
  {
    "uri" : "http://hl7.org.au/fhir/core/ImplementationGuide/hl7.fhir.au.core",
    "packageId" : "hl7.fhir.au.core",
    "version" : "2.0.0"
  }],
  "definition" : {
    "extension" : [{
      "extension" : [{
        "url" : "code",
        "valueString" : "copyrightyear"
      },
      {
        "url" : "value",
        "valueString" : "2024+"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "releaselabel"
      },
      {
        "url" : "value",
        "valueString" : "CI Build"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "shownav"
      },
      {
        "url" : "value",
        "valueString" : "false"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "dynamic-source-viewers"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "show-inherited-invariants"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "excludemap"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-expansion-params"
      },
      {
        "url" : "value",
        "valueString" : "../input/_resources/exp-params.json"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "fmm-definition"
      },
      {
        "url" : "value",
        "valueString" : "https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "ips-comparison"
      },
      {
        "url" : "value",
        "valueString" : "current"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "autoload-resources"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-liquid"
      },
      {
        "url" : "value",
        "valueString" : "template/liquid"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-liquid"
      },
      {
        "url" : "value",
        "valueString" : "input/liquid"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-qa"
      },
      {
        "url" : "value",
        "valueString" : "temp/qa"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-temp"
      },
      {
        "url" : "value",
        "valueString" : "temp/pages"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-output"
      },
      {
        "url" : "value",
        "valueString" : "output"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-suppressed-warnings"
      },
      {
        "url" : "value",
        "valueString" : "input/ignoreWarnings.txt"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "path-history"
      },
      {
        "url" : "value",
        "valueString" : "http://hl7.org.au/fhir/ps/history.html"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "template-html"
      },
      {
        "url" : "value",
        "valueString" : "template-page.html"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "template-md"
      },
      {
        "url" : "value",
        "valueString" : "template-page-md.html"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-contact"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-context"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-copyright"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-jurisdiction"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-license"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-publisher"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-version"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "apply-wg"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "active-tables"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "propagate-status"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "excludelogbinaryformat"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueString" : "tabbed-snapshots"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/expansion-parameters",
      "valueReference" : {
        "reference" : "Parameters/expansion-parameters"
      }
    },
    {
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-internal-dependency",
      "valueCode" : "hl7.fhir.uv.tools.r4#1.1.2"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "copyrightyear"
      },
      {
        "url" : "value",
        "valueString" : "2024+"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "releaselabel"
      },
      {
        "url" : "value",
        "valueString" : "CI Build"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "shownav"
      },
      {
        "url" : "value",
        "valueString" : "false"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "dynamic-source-viewers"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "show-inherited-invariants"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "excludemap"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-expansion-params"
      },
      {
        "url" : "value",
        "valueString" : "../input/_resources/exp-params.json"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "fmm-definition"
      },
      {
        "url" : "value",
        "valueString" : "https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "ips-comparison"
      },
      {
        "url" : "value",
        "valueString" : "current"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "autoload-resources"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-liquid"
      },
      {
        "url" : "value",
        "valueString" : "template/liquid"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-liquid"
      },
      {
        "url" : "value",
        "valueString" : "input/liquid"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-qa"
      },
      {
        "url" : "value",
        "valueString" : "temp/qa"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-temp"
      },
      {
        "url" : "value",
        "valueString" : "temp/pages"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-output"
      },
      {
        "url" : "value",
        "valueString" : "output"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-suppressed-warnings"
      },
      {
        "url" : "value",
        "valueString" : "input/ignoreWarnings.txt"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "path-history"
      },
      {
        "url" : "value",
        "valueString" : "http://hl7.org.au/fhir/ps/history.html"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "template-html"
      },
      {
        "url" : "value",
        "valueString" : "template-page.html"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "template-md"
      },
      {
        "url" : "value",
        "valueString" : "template-page-md.html"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-contact"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-context"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-copyright"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-jurisdiction"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-license"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-publisher"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-version"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "apply-wg"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "active-tables"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "propagate-status"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "excludelogbinaryformat"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    },
    {
      "extension" : [{
        "url" : "code",
        "valueCode" : "tabbed-snapshots"
      },
      {
        "url" : "value",
        "valueString" : "true"
      }],
      "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
    }],
    "resource" : [{
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "ActorDefinition"
      }],
      "reference" : {
        "reference" : "ActorDefinition/au-ps-actor-consumer"
      },
      "name" : "AU PS Consumer",
      "description" : "An AU PS Consumer is a system that consumes an AU PS Bundle and uses it to display or process patient summary content. This actor is based on the Consumer (IPS) actor, and describes the additional requirements and documentation applied for the Australian context.",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "ActorDefinition"
      }],
      "reference" : {
        "reference" : "ActorDefinition/au-ps-actor-producer"
      },
      "name" : "AU PS Producer",
      "description" : "An AU PS Producer is a system which creates or assembles an AU PS Bundle through automated generation or human curation of the patient summary content. This actor is based on the Creator (IPS) actor, and describes the additional requirements and documentation applied for the Australian context.",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-allergyintolerance"
      },
      "name" : "AU PS AllergyIntolerance",
      "description" : "This profile sets minimum expectations for an AllergyIntolerance resource in the context of a patient summary in an Australian context. It is based on the [AU Core AllergyIntolerance](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html) profile, and applies the additional requirements from [AllergyIntolerance (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/AllergyIntolerance-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-bundle"
      },
      "name" : "AU PS Bundle",
      "description" : "This profile sets minimum expectations for a Bundle resource in the context of a patient summary in an Australian context. It is based on FHIR [Bundle](http://hl7.org/fhir/StructureDefinition/Bundle), and applies the constraints of [Bundle (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Bundle-uv-ips) and AU Patient Summary (AU PS).\r\nAU PS is specified in this guide as a HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable 'minimal' data blocks (the AU PS profiles).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-composition"
      },
      "name" : "AU PS Composition",
      "description" : "This profile sets minimum expectations for a Composition resource in the context of a patient summary in an Australian context. It is based on [AU Base Composition](http://hl7.org.au/fhir/StructureDefinition/au-composition) and imposes [Composition (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Composition-uv-ips). \r\nAU Patient Summary (AU PS) is specified in this guide as a HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable 'minimal' data blocks (the AU PS profiles).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-condition"
      },
      "name" : "AU PS Condition",
      "description" : "This profile sets minimum expectations for a Condition resource in the context of a patient summary in an Australian context. It is based on the [AU Core Condition](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-condition.html) profile, and applies the additional requirements from [Condition (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Condition-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-encounter"
      },
      "name" : "AU PS Encounter",
      "description" : "This profile sets minimum expectations for an Encounter resource in the context of a patient summary in an Australian context. It is based on the [AU Core Encounter](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-encounter.html) profile, and applies the additional constraints for use in a patient summary context consistent with the profiling conventions of [IPS](https://hl7.org/fhir/uv/ips/STU2/).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-immunization"
      },
      "name" : "AU PS Immunization",
      "description" : "This profile sets minimum expectations for an Immunization resource in the context of a patient summary in an Australian context. It is based on the [AU Core Immunization](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-immunization.html) profile, and applies the additional requirements from [Immunization (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Immunization-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-medication"
      },
      "name" : "AU PS Medication",
      "description" : "This profile sets minimum expectations for a Medication resource in the context of a patient summary in an Australian context. It is based on the [AU Core Medication](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medication.html) profile, and applies the additional requirements from [Medication (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Medication-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-medicationrequest"
      },
      "name" : "AU PS MedicationRequest",
      "description" : "This profile sets minimum expectations for a MedicationRequest resource in the context of a patient summary in an Australian context. It is based on the [AU Core MedicationRequest](http://hl7.org.au/fhir/core/StructureDefinition/au-core-medicationrequest) profile, and applies the additional requirements from [MedicationRequest (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/MedicationRequest-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-medicationstatement"
      },
      "name" : "AU PS MedicationStatement",
      "description" : "This profile sets minimum expectations for a MedicationStatement resource in the context of a patient summary in an Australian context. It is based on the [AU Core MedicationStatement](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medicationstatement.html) profile, and applies the additional requirements from [MedicationStatement (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/MedicationStatement-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-organization"
      },
      "name" : "AU PS Organization",
      "description" : "This profile sets minimum expectations for an Organization resource in the context of a patient summary in an Australian context. It is based on the [AU Core Organization](http://hl7.org.au/fhir/core/StructureDefinition/au-core-organization) profile, and applies the additional requirements from [Organization (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Organization-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-practitioner"
      },
      "name" : "AU PS Practitioner",
      "description" : "This profile sets minimum expectations for a Practitioner resource in the context of a patient summary in an Australian context. It is based on the [AU Core Practitioner](http://hl7.org.au/fhir/core/StructureDefinition/au-core-practitioner) profile, and applies the additional requirements from [Practitioner (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Practitioner-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-practitionerrole"
      },
      "name" : "AU PS PractitionerRole",
      "description" : "This profile sets minimum expectations for a PractitionerRole resource in the context of a patient summary in an Australian context. It is based on the [AU Core PractitionerRole](http://hl7.org.au/fhir/core/StructureDefinition/au-core-practitionerrole) profile, and applies the additional requirements from [PractitionerRole (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/PractitionerRole-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-procedure"
      },
      "name" : "AU PS Procedure",
      "description" : "This profile sets minimum expectations for a Procedure resource in the context of a patient summary in an Australian context. It is based on the [AU Core Procedure](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html) profile, and applies the additional requirements from [Procedure (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Procedure-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-relatedperson"
      },
      "name" : "AU PS RelatedPerson",
      "description" : "This profile sets minimum expectations for a RelatedPerson resource in the context of a patient summary in an Australian context. It is based on the [AU Core Related Person](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-relatedperson.html) profile, and applies the additional constraints for use in a patient summary context consistent with the profiling conventions of [IPS](https://hl7.org/fhir/uv/ips/STU2/).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-smokingstatus"
      },
      "name" : "AU PS Smoking Status",
      "description" : "This profile sets minimum expectations for an Observation resource that represents a patient's smoking status in the context of a patient summary in an Australian context. It is based on the [AU Core Smoking Status](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-smokingstatus.html) profile, and applies the additional requirements from [Observation Social History - Tobacco Use (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-tobaccouse-uv-ips).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-diagnosticresult-path"
      },
      "name" : "AU PS Pathology Result Observation",
      "description" : "This profile sets minimum expectations for an Observation resource that represents a pathology result associated with a patient in the context of a patient summary in an Australian context. It is based on the [AU Core Pathology Result Observation](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-diagnosticresult-path.html) profile, and applies the additional requirements from [Observation Results - Laboratory/Pathology (IPS)](https://hl7.org/fhir/uv/ips/STU2/StructureDefinition-Observation-results-laboratory-pathology-uv-ips.html).",
      "exampleBoolean" : false
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "Bundle"
      }],
      "reference" : {
        "reference" : "Bundle/aups-section-emptyreason"
      },
      "name" : "Section empty reason",
      "description" : "Shows a software-assembled patient summary that demonstrates missing data for Patient.birthDate and suppressed data for Patient.gender and Patient.identifier using the Data Absent Reason extension. The system also has no information for the sections: problems, allergies, medications, and immunisations. Example for the *AU PS Bundle* and *AU PS Composition* profiles. Patient: Ronny Lawrence Irvine.",
      "exampleCanonical" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle"
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "Bundle"
      }],
      "reference" : {
        "reference" : "Bundle/aups-noknownx"
      },
      "name" : "No Known X",
      "description" : "Shows an example of a patient summary that demonstrates no known problems or disabilities, no known allergies and intolerances, and no known current medications. Example for the *AU PS Bundle* and *AU PS Composition* profiles. Patient: Charlotte Morris.",
      "exampleCanonical" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle"
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "Bundle"
      }],
      "reference" : {
        "reference" : "Bundle/aups-basicsummary"
      },
      "name" : "Basic Summary",
      "description" : "Shows an example of a provider curated patient summary that demonstrates no known problems or disabilities, current allergies and intolerances, and current medication use. Example for the *AU PS Bundle* and *AU PS Composition* profiles. Patient: Mia Leanne Banks.",
      "exampleCanonical" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle"
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "Bundle"
      }],
      "reference" : {
        "reference" : "Bundle/aups-referral-endoconsult-curated"
      },
      "name" : "Joyce 28 October",
      "description" : "[Referral to Specialist and Allied Health use case](uc-referral.html) example. Shows an example of a patient summary containing the medical history and current medications at the time of referral that was authored by the GP through curation of a generated view of the data within their clinical information system, and was attested at the time of creation of the patient summary and signed electronically. Example for the *AU PS Bundle* and *AU PS Composition* profiles. Patient: Joyce Johnson.",
      "exampleCanonical" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle"
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "Bundle"
      }],
      "reference" : {
        "reference" : "Bundle/aups-referral-endoconsult-autogen"
      },
      "name" : "Joyce 07 November 2024",
      "description" : "[Referral to Specialist and Allied Health use case](uc-referral.html) example. Shows an example of a patient summary containing the medical history and current medications that is automatically generated by a clinical information system and includes the most recent information. This example is digitally signed. Example for the *AU PS Bundle* and *AU PS Composition* profiles. Patient: Joyce Johnson.",
      "exampleCanonical" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle"
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "Bundle"
      }],
      "reference" : {
        "reference" : "Bundle/aups-gpvisit-retrieval"
      },
      "name" : "Jeramy 27 May",
      "description" : "[Interstate GP use case](uc-interstate.html) example. Shows an example of a patient summary authored by the patient's usual GP that was updated after a recent admission to hospital. Example for the *AU PS Bundle* and *AU PS Composition* profiles. Patient: Jeramy Ezra Banks.",
      "exampleCanonical" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle"
    },
    {
      "extension" : [{
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
        "valueString" : "StructureDefinition:resource"
      }],
      "reference" : {
        "reference" : "StructureDefinition/au-ps-patient"
      },
      "name" : "AU PS Patient",
      "description" : "This profile sets minimum expectations for a Patient resource in the context of a patient summary in an Australian context. It is based on the [AU Core Patient](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-patient.html) profile, and applies the additional requirements from [Patient (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Patient-uv-ips)."
    }],
    "page" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
        "valueCode" : "informative"
      },
      {
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
        "valueUrl" : "toc.html"
      }],
      "nameUrl" : "toc.html",
      "title" : "Table of Contents",
      "generation" : "html",
      "page" : [{
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "index.html"
        }],
        "nameUrl" : "index.html",
        "title" : "Home",
        "generation" : "markdown"
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "conformance.html"
        }],
        "nameUrl" : "conformance.html",
        "title" : "Conformance",
        "generation" : "markdown",
        "page" : [{
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "general-requirements.html"
          }],
          "nameUrl" : "general-requirements.html",
          "title" : "General Requirements",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "declaring-conformance.html"
          }],
          "nameUrl" : "declaring-conformance.html",
          "title" : "Declaring Conformance",
          "generation" : "markdown"
        }]
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "the-aups.html"
        }],
        "nameUrl" : "the-aups.html",
        "title" : "The AU PS",
        "generation" : "markdown"
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "guidance.html"
        }],
        "nameUrl" : "guidance.html",
        "title" : "Guidance",
        "generation" : "markdown",
        "page" : [{
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "general-guidance.html"
          }],
          "nameUrl" : "general-guidance.html",
          "title" : "General Guidance",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "generation-and-access.html"
          }],
          "nameUrl" : "generation-and-access.html",
          "title" : "Generation and Access",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "sex-and-gender.html"
          }],
          "nameUrl" : "sex-and-gender.html",
          "title" : "Sex and Gender",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "aucdi.html"
          }],
          "nameUrl" : "aucdi.html",
          "title" : "AUCDI",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "relationship.html"
          }],
          "nameUrl" : "relationship.html",
          "title" : "Relationship With Other IGs",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "variance.html"
          }],
          "nameUrl" : "variance.html",
          "title" : "AU Variance Statement",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "comparison.html"
          }],
          "nameUrl" : "comparison.html",
          "title" : "Comparison With Other National and International IGs",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "future.html"
          }],
          "nameUrl" : "future.html",
          "title" : "Future of AU Patient Summary",
          "generation" : "markdown"
        }]
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "usecase.html"
        }],
        "nameUrl" : "usecase.html",
        "title" : "Use Cases",
        "generation" : "markdown",
        "page" : [{
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "uc-interstate.html"
          }],
          "nameUrl" : "uc-interstate.html",
          "title" : "Interstate GP Visit",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "uc-referral.html"
          }],
          "nameUrl" : "uc-referral.html",
          "title" : "Referral to Specialist and Allied Health",
          "generation" : "markdown"
        }]
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "security.html"
        }],
        "nameUrl" : "security.html",
        "title" : "Security and Privacy",
        "generation" : "markdown"
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "artefacts.html"
        }],
        "nameUrl" : "artefacts.html",
        "title" : "FHIR artefacts",
        "generation" : "markdown",
        "page" : [{
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "artifacts.html"
          }],
          "nameUrl" : "artifacts.html",
          "title" : "Artefacts Summary",
          "generation" : "html"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "profiles-and-extensions.html"
          }],
          "nameUrl" : "profiles-and-extensions.html",
          "title" : "Profiles and Extensions",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "terminology.html"
          }],
          "nameUrl" : "terminology.html",
          "title" : "Terminology",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "actors.html"
          }],
          "nameUrl" : "actors.html",
          "title" : "Actor Definitions",
          "generation" : "markdown"
        }]
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "examples.html"
        }],
        "nameUrl" : "examples.html",
        "title" : "Examples",
        "generation" : "markdown"
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "support.html"
        }],
        "nameUrl" : "support.html",
        "title" : "Support",
        "generation" : "markdown",
        "page" : [{
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "downloads.html"
          }],
          "nameUrl" : "downloads.html",
          "title" : "Downloads",
          "generation" : "markdown"
        },
        {
          "extension" : [{
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
            "valueCode" : "informative"
          },
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
            "valueUrl" : "license.html"
          }],
          "nameUrl" : "license.html",
          "title" : "License and Legal",
          "generation" : "markdown"
        }]
      },
      {
        "extension" : [{
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "changes.html"
        }],
        "nameUrl" : "changes.html",
        "title" : "Change Log",
        "generation" : "markdown"
      }]
    },
    "parameter" : [{
      "code" : "path-resource",
      "value" : "input/resources"
    },
    {
      "code" : "path-resource",
      "value" : "input/capabilities"
    },
    {
      "code" : "path-resource",
      "value" : "input/examples"
    },
    {
      "code" : "path-resource",
      "value" : "input/extensions"
    },
    {
      "code" : "path-resource",
      "value" : "input/models"
    },
    {
      "code" : "path-resource",
      "value" : "input/operations"
    },
    {
      "code" : "path-resource",
      "value" : "input/profiles"
    },
    {
      "code" : "path-resource",
      "value" : "input/vocabulary"
    },
    {
      "code" : "path-resource",
      "value" : "input/testing"
    },
    {
      "code" : "path-resource",
      "value" : "input/history"
    },
    {
      "code" : "path-resource",
      "value" : "fsh-generated/resources"
    },
    {
      "code" : "path-pages",
      "value" : "template/config"
    },
    {
      "code" : "path-pages",
      "value" : "input/images"
    },
    {
      "code" : "path-tx-cache",
      "value" : "input-cache/txcache"
    }]
  }
}

```
