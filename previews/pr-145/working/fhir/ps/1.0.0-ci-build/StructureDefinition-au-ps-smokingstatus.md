# AU PS Smoking Status - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* [**Artefacts Summary**](artifacts.md)
* **AU PS Smoking Status**

## Resource Profile: AU PS Smoking Status 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-smokingstatus | *Version*:1.0.0-ci-build | |
| * Standards status: *[Draft](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels): 2 | *Computable Name*:AUPSSmokingStatus |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved. | | |

 
This profile sets minimum expectations for an Observation resource that represents a patient's smoking status in the context of a patient summary in an Australian context. It is based on the [AU Core Smoking Status](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-smokingstatus.html) profile, and applies the additional requirements from [Observation Social History - Tobacco Use (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-tobaccouse-uv-ips). 

See [Comparison With Other National and International IGs](comparison.md) for a comparison between AU Patient Summary (AU PS) profiles and profiles in other implementation guides.

### Profile Specific Implementation Guidance

* See the [guidance on implementing the smoking status Observation resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-smokingstatus.html#profile-specific-implementation-guidance) in AU Core.

**Examples for this Profile**: [Bundle/aups-referral-endoconsult-autogen](Bundle-aups-referral-endoconsult-autogen.md) and [Bundle/aups-referral-endoconsult-curated](Bundle-aups-referral-endoconsult-curated.md)

**Usages:**

* Use this Profile: [AU PS Bundle](StructureDefinition-au-ps-bundle.md)
* Refer to this Profile: [AU PS Composition](StructureDefinition-au-ps-composition.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/hl7.fhir.au.ps|current/StructureDefinition/StructureDefinition-au-ps-smokingstatus.json)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-au-ps-smokingstatus.csv), [Excel](StructureDefinition-au-ps-smokingstatus.xlsx), [Schematron](StructureDefinition-au-ps-smokingstatus.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "au-ps-smokingstatus",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 2
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-compliesWithProfile",
    "valueCanonical" : "http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-tobaccouse-uv-ips"
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
  "url" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-smokingstatus",
  "version" : "1.0.0-ci-build",
  "name" : "AUPSSmokingStatus",
  "title" : "AU PS Smoking Status",
  "status" : "active",
  "date" : "2026-06-19T03:09:13+00:00",
  "publisher" : "HL7 Australia",
  "contact" : [{
    "name" : "HL7 Australia FHIR Work Group",
    "telecom" : [{
      "system" : "url",
      "value" : "https://confluence.hl7.org/display/HAFWG",
      "use" : "work"
    }]
  }],
  "description" : "This profile sets minimum expectations for an Observation resource that represents a patient's smoking status in the context of a patient summary in an Australian context. It is based on the [AU Core Smoking Status](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-smokingstatus.html) profile, and applies the additional requirements from [Observation Social History - Tobacco Use (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Observation-tobaccouse-uv-ips).",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "AU"
    }]
  }],
  "copyright" : "Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved.",
  "fhirVersion" : "4.0.1",
  "mapping" : [{
    "identity" : "workflow",
    "uri" : "http://hl7.org/fhir/workflow",
    "name" : "Workflow Pattern"
  },
  {
    "identity" : "sct-concept",
    "uri" : "http://snomed.info/conceptdomain",
    "name" : "SNOMED CT Concept Domain Binding"
  },
  {
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
    "identity" : "w5",
    "uri" : "http://hl7.org/fhir/fivews",
    "name" : "FiveWs Pattern Mapping"
  },
  {
    "identity" : "sct-attr",
    "uri" : "http://snomed.org/attributebinding",
    "name" : "SNOMED CT Attribute Binding"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Observation",
  "baseDefinition" : "http://hl7.org.au/fhir/core/StructureDefinition/au-core-smokingstatus",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Observation",
      "path" : "Observation"
    },
    {
      "id" : "Observation.status",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate-if-known"
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
      "path" : "Observation.status"
    },
    {
      "id" : "Observation.category",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate-if-known"
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
      "path" : "Observation.category",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Observation.category:socialHistory",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate-if-known"
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
      "path" : "Observation.category",
      "sliceName" : "socialHistory",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Observation.code",
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
      "path" : "Observation.code",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Observation.code.coding",
      "path" : "Observation.code.coding",
      "min" : 2
    },
    {
      "id" : "Observation.code.coding:loincSmokingStatus",
      "path" : "Observation.code.coding",
      "sliceName" : "loincSmokingStatus",
      "min" : 1
    },
    {
      "id" : "Observation.subject",
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
      "path" : "Observation.subject",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-patient"]
      }]
    },
    {
      "id" : "Observation.subject.reference",
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
      "path" : "Observation.subject.reference",
      "min" : 1,
      "mustSupport" : true
    },
    {
      "id" : "Observation.effective[x]",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate-if-known"
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
      "path" : "Observation.effective[x]"
    },
    {
      "id" : "Observation.value[x]",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate-if-known"
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
      "path" : "Observation.value[x]",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Observation.dataAbsentReason",
      "extension" : [{
        "extension" : [{
          "url" : "code",
          "valueCode" : "SHALL:populate-if-known"
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
      "path" : "Observation.dataAbsentReason",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Observation.component",
      "path" : "Observation.component",
      "max" : "0"
    }]
  }
}

```
