# AU PS Bundle - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* [**Artefacts Summary**](artifacts.md)
* **AU PS Bundle**

## Resource Profile: AU PS Bundle 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle | *Version*:1.0.0-ci-build | |
| * Standards status: *[Draft](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels): 2 | *Computable Name*:AUPSBundle |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved. | | |

 
This profile sets minimum expectations for a Bundle resource in the context of a patient summary in an Australian context. It is based on FHIR [Bundle](http://hl7.org/fhir/StructureDefinition/Bundle), and applies the constraints of [Bundle (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Bundle-uv-ips) and AU Patient Summary (AU PS). AU PS is specified in this guide as a HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable 'minimal' data blocks (the AU PS profiles). 

See [Comparison With Other National and International IGs](comparison.md) for a comparison between AU Patient Summary (AU PS) profiles and profiles in other implementation guides.

### Profile specific implementation guidance

* Implementers populating a bundle entry with an unprofiled resource type, e.g. MedicationAdministration, are recommended to consider the corresponding [AU Base](https://build.fhir.org/ig/hl7au/au-fhir-base/) profile, e.g. [AU Base MedicationAdministration](https://build.fhir.org/ig/hl7au/au-fhir-base/StructureDefinition-au-medicationadministration.html), as guidance for that resource type in an Australian healthcare context.

**Usages:**

* Examples for this Profile: [Bundle/aups-basicsummary](Bundle-aups-basicsummary.md), [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.md), [Bundle/aups-noknownx](Bundle-aups-noknownx.md), [Bundle/aups-referral-endoconsult-autogen](Bundle-aups-referral-endoconsult-autogen.md)... Show 2 more, [Bundle/aups-referral-endoconsult-curated](Bundle-aups-referral-endoconsult-curated.md) and [Bundle/aups-section-emptyreason](Bundle-aups-section-emptyreason.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/hl7.fhir.au.ps|current/StructureDefinition/StructureDefinition-au-ps-bundle.json)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-au-ps-bundle.csv), [Excel](StructureDefinition-au-ps-bundle.xlsx), [Schematron](StructureDefinition-au-ps-bundle.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "au-ps-bundle",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 2
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-compliesWithProfile",
    "valueCanonical" : "http://hl7.org/fhir/uv/ips/StructureDefinition/Bundle-uv-ips"
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
    "valueCode" : "draft",
    "_valueCode" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "http://hl7.org.au/fhir/ps/ImplementationGuide/hl7.fhir.au.ps"
      }]
    }
  }],
  "url" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-bundle",
  "version" : "1.0.0-ci-build",
  "name" : "AUPSBundle",
  "title" : "AU PS Bundle",
  "status" : "active",
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
  "description" : "This profile sets minimum expectations for a Bundle resource in the context of a patient summary in an Australian context. It is based on FHIR [Bundle](http://hl7.org/fhir/StructureDefinition/Bundle), and applies the constraints of [Bundle (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Bundle-uv-ips) and AU Patient Summary (AU PS).\r\nAU PS is specified in this guide as a HL7 FHIR document (a Bundle including a Composition), composed by a set of potentially reusable 'minimal' data blocks (the AU PS profiles).",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "AU"
    }]
  }],
  "copyright" : "Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved.",
  "fhirVersion" : "4.0.1",
  "mapping" : [{
    "identity" : "v2",
    "uri" : "http://hl7.org/v2",
    "name" : "HL7 v2 Mapping"
  },
  {
    "identity" : "rim",
    "uri" : "http://hl7.org/v3",
    "name" : "RIM Mapping"
  },
  {
    "identity" : "cda",
    "uri" : "http://hl7.org/v3/cda",
    "name" : "CDA (R2)"
  },
  {
    "identity" : "w5",
    "uri" : "http://hl7.org/fhir/fivews",
    "name" : "FiveWs Pattern Mapping"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Bundle",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Bundle",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Bundle",
      "path" : "Bundle",
      "short" : "AU Patient Summary Bundle",
      "definition" : "AU Patient Summary Bundle. A container for a collection of resources in the patient summary document in an Australian healthcare context.",
      "constraint" : [{
        "key" : "bdl-ips-1",
        "severity" : "error",
        "human" : "An IPS document must have no additional Composition (including Composition subclass) resources besides the first.",
        "expression" : "entry.tail().where(resource is Composition).empty()"
      }]
    },
    {
      "id" : "Bundle.identifier",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.identifier",
      "min" : 1,
      "mustSupport" : true
    },
    {
      "id" : "Bundle.type",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.type",
      "fixedCode" : "document",
      "mustSupport" : true
    },
    {
      "id" : "Bundle.timestamp",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.timestamp",
      "min" : 1,
      "mustSupport" : true
    },
    {
      "id" : "Bundle.entry",
      "path" : "Bundle.entry",
      "slicing" : {
        "discriminator" : [{
          "type" : "type",
          "path" : "resource"
        }],
        "rules" : "open"
      },
      "short" : "Entry resource in the patient summary bundle",
      "definition" : "An entry resource included in the patient summary document bundle resource.",
      "comment" : "The Composition is the first entry (only a single Composition resource instance can be included) and a Patient resource.  Additional constraints are specified in the AU PS Composition profile.",
      "min" : 2
    },
    {
      "id" : "Bundle.entry.fullUrl",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.entry.fullUrl",
      "min" : 1,
      "mustSupport" : true
    },
    {
      "id" : "Bundle.entry.search",
      "path" : "Bundle.entry.search",
      "max" : "0"
    },
    {
      "id" : "Bundle.entry.request",
      "path" : "Bundle.entry.request",
      "max" : "0"
    },
    {
      "id" : "Bundle.entry.response",
      "path" : "Bundle.entry.response",
      "max" : "0"
    },
    {
      "id" : "Bundle.entry:composition",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHOULD:display"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.entry",
      "sliceName" : "composition",
      "min" : 1,
      "max" : "1",
      "mustSupport" : true
    },
    {
      "id" : "Bundle.entry:composition.resource",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Composition",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-composition"]
      }],
      "mustSupport" : true
    },
    {
      "id" : "Bundle.entry:patient",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.entry",
      "sliceName" : "patient",
      "min" : 1,
      "max" : "1",
      "mustSupport" : true
    },
    {
      "id" : "Bundle.entry:patient.resource",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-producer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      },
      {
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:handle"
        },
        {
          "url" : "actor",
          "valueCanonical" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
        }],
        "url" : "http://hl7.org/fhir/StructureDefinition/obligation"
      }],
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Patient",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-patient"]
      }],
      "mustSupport" : true
    },
    {
      "id" : "Bundle.entry:allergyintolerance",
      "path" : "Bundle.entry",
      "sliceName" : "allergyintolerance",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:allergyintolerance.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "AllergyIntolerance",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-allergyintolerance"]
      }]
    },
    {
      "id" : "Bundle.entry:careteam",
      "path" : "Bundle.entry",
      "sliceName" : "careteam",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:careteam.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "CareTeam"
      }]
    },
    {
      "id" : "Bundle.entry:clinicalimpression",
      "path" : "Bundle.entry",
      "sliceName" : "clinicalimpression",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:clinicalimpression.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "ClinicalImpression"
      }]
    },
    {
      "id" : "Bundle.entry:condition",
      "path" : "Bundle.entry",
      "sliceName" : "condition",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:condition.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Condition",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-condition"]
      }]
    },
    {
      "id" : "Bundle.entry:consent",
      "path" : "Bundle.entry",
      "sliceName" : "consent",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:consent.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Consent"
      }]
    },
    {
      "id" : "Bundle.entry:device",
      "path" : "Bundle.entry",
      "sliceName" : "device",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:device.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Device"
      }]
    },
    {
      "id" : "Bundle.entry:deviceusestatement",
      "path" : "Bundle.entry",
      "sliceName" : "deviceusestatement",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:deviceusestatement.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "DeviceUseStatement",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/DeviceUseStatement-uv-ips"]
      }]
    },
    {
      "id" : "Bundle.entry:diagnosticreport",
      "path" : "Bundle.entry",
      "sliceName" : "diagnosticreport",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:diagnosticreport.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "DiagnosticReport",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/DiagnosticReport-uv-ips"]
      }]
    },
    {
      "id" : "Bundle.entry:documentreference",
      "path" : "Bundle.entry",
      "sliceName" : "documentreference",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:documentreference.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "DocumentReference"
      }]
    },
    {
      "id" : "Bundle.entry:encounter",
      "path" : "Bundle.entry",
      "sliceName" : "encounter",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:encounter.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Encounter",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-encounter"]
      }]
    },
    {
      "id" : "Bundle.entry:flag",
      "path" : "Bundle.entry",
      "sliceName" : "flag",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:flag.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Flag",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/Flag-alert-uv-ips"]
      }]
    },
    {
      "id" : "Bundle.entry:imagingstudy",
      "path" : "Bundle.entry",
      "sliceName" : "imagingstudy",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:imagingstudy.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "ImagingStudy",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/ImagingStudy-uv-ips"]
      }]
    },
    {
      "id" : "Bundle.entry:immunization",
      "path" : "Bundle.entry",
      "sliceName" : "immunization",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:immunization.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Immunization",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-immunization"]
      }]
    },
    {
      "id" : "Bundle.entry:immunizationRecommendation",
      "path" : "Bundle.entry",
      "sliceName" : "immunizationRecommendation",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:immunizationRecommendation.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "ImmunizationRecommendation"
      }]
    },
    {
      "id" : "Bundle.entry:location",
      "path" : "Bundle.entry",
      "sliceName" : "location",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:location.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Location",
        "profile" : ["http://hl7.org.au/fhir/core/StructureDefinition/au-core-location"]
      }]
    },
    {
      "id" : "Bundle.entry:medication",
      "path" : "Bundle.entry",
      "sliceName" : "medication",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:medication.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Medication",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-medication"]
      }]
    },
    {
      "id" : "Bundle.entry:medicationrequest",
      "path" : "Bundle.entry",
      "sliceName" : "medicationrequest",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:medicationrequest.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "MedicationRequest",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-medicationrequest"]
      }]
    },
    {
      "id" : "Bundle.entry:medicationstatement",
      "path" : "Bundle.entry",
      "sliceName" : "medicationstatement",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:medicationstatement.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "MedicationStatement",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-medicationstatement"]
      }]
    },
    {
      "id" : "Bundle.entry:observation",
      "path" : "Bundle.entry",
      "sliceName" : "observation",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:observation.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Observation",
        "profile" : ["http://hl7.org/fhir/StructureDefinition/Observation",
        "http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-pregnancy-edd-uv-ips",
        "http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-pregnancy-outcome-uv-ips",
        "http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-pregnancy-status-uv-ips",
        "http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-alcoholuse-uv-ips",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-smokingstatus",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-diagnosticresult-path",
        "http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-results-radiology-uv-ips",
        "http://hl7.org/fhir/StructureDefinition/vitalsigns",
        "http://hl7.org.au/fhir/core/StructureDefinition/au-core-bloodpressure",
        "http://hl7.org.au/fhir/core/StructureDefinition/au-core-bodyheight",
        "http://hl7.org.au/fhir/core/StructureDefinition/au-core-bodytemp",
        "http://hl7.org.au/fhir/core/StructureDefinition/au-core-bodyweight",
        "http://hl7.org.au/fhir/core/StructureDefinition/au-core-heartrate",
        "http://hl7.org.au/fhir/core/StructureDefinition/au-core-resprate",
        "http://hl7.org.au/fhir/core/StructureDefinition/au-core-waistcircum"]
      }]
    },
    {
      "id" : "Bundle.entry:organization",
      "path" : "Bundle.entry",
      "sliceName" : "organization",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:organization.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Organization",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-organization"]
      }]
    },
    {
      "id" : "Bundle.entry:practitioner",
      "path" : "Bundle.entry",
      "sliceName" : "practitioner",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:practitioner.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Practitioner",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-practitioner"]
      }]
    },
    {
      "id" : "Bundle.entry:practitionerrole",
      "path" : "Bundle.entry",
      "sliceName" : "practitionerrole",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:practitionerrole.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "PractitionerRole",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-practitionerrole"]
      }]
    },
    {
      "id" : "Bundle.entry:procedure",
      "path" : "Bundle.entry",
      "sliceName" : "procedure",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:procedure.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Procedure",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-procedure"]
      }]
    },
    {
      "id" : "Bundle.entry:relatedperson",
      "path" : "Bundle.entry",
      "sliceName" : "relatedperson",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:relatedperson.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "RelatedPerson",
        "profile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-relatedperson"]
      }]
    },
    {
      "id" : "Bundle.entry:specimen",
      "path" : "Bundle.entry",
      "sliceName" : "specimen",
      "min" : 0,
      "max" : "*"
    },
    {
      "id" : "Bundle.entry:specimen.resource",
      "path" : "Bundle.entry.resource",
      "min" : 1,
      "type" : [{
        "code" : "Specimen",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/Specimen-uv-ips"]
      }]
    }]
  }
}

```
