# AU PS Procedure - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* [**Artefacts Summary**](artifacts.md)
* **AU PS Procedure**

## Resource Profile: AU PS Procedure 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-procedure | *Version*:1.0.0-ci-build | |
| * Standards status: *[Draft](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels): 2 | *Computable Name*:AUPSProcedure |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved. | | |

 
This profile sets minimum expectations for a Procedure resource in the context of a patient summary in an Australian context. It is based on the [AU Core Procedure](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html) profile, and applies the additional requirements from [Procedure (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Procedure-uv-ips). 

See [Comparison With Other National and International IGs](comparison.md) for a comparison between AU Patient Summary (AU PS) profiles and profiles in other implementation guides.

### Profile Specific Implementation Guidance

* See the [guidance on implementing the Procedure resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html#profile-specific-implementation-guidance) in AU Core.
* The Procedure resource can represent a clinical indication with `Procedure.reasonCode`, or a reference with `Procedure.reasonReference` to a Condition or other resource. 
* Although both are marked as **Must Support**, producers are not required to support both a code and a reference, but they **SHALL** support **at least one** of these elements
* A consumer **SHALL** support both elements
 

The additional obligation on `Procedure.performedDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.md) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.md), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the Formal Views of Profile Content. See [Zulip discussion](https://chat.fhir.org/#narrow/channel/179252-IG-creation/topic/Obligation.20Extension.20on.20ElementDefinition.2Etype.20not.20rendering) for more information.

**Examples for this Profile**: [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.md)

**Usages:**

* Use this Profile: [AU PS Bundle](StructureDefinition-au-ps-bundle.md)
* Refer to this Profile: [AU PS Composition](StructureDefinition-au-ps-composition.md), [AU PS Encounter](StructureDefinition-au-ps-encounter.md) and [AU PS Procedure](StructureDefinition-au-ps-procedure.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/hl7.fhir.au.ps|current/StructureDefinition/StructureDefinition-au-ps-procedure.json)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-au-ps-procedure.csv), [Excel](StructureDefinition-au-ps-procedure.xlsx), [Schematron](StructureDefinition-au-ps-procedure.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "au-ps-procedure",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 2
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-compliesWithProfile",
    "valueCanonical" : "http://hl7.org/fhir/uv/ips/StructureDefinition/Procedure-uv-ips"
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
  "url" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-procedure",
  "version" : "1.0.0-ci-build",
  "name" : "AUPSProcedure",
  "title" : "AU PS Procedure",
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
  "description" : "This profile sets minimum expectations for a Procedure resource in the context of a patient summary in an Australian context. It is based on the [AU Core Procedure](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-procedure.html) profile, and applies the additional requirements from [Procedure (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Procedure-uv-ips).",
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
    "identity" : "v2",
    "uri" : "http://hl7.org/v2",
    "name" : "HL7 v2 Mapping"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Procedure",
  "baseDefinition" : "http://hl7.org.au/fhir/core/StructureDefinition/au-core-procedure",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Procedure",
      "path" : "Procedure"
    },
    {
      "id" : "Procedure.status",
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
      "path" : "Procedure.status"
    },
    {
      "id" : "Procedure.code",
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
      "path" : "Procedure.code",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Procedure.subject",
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
      "path" : "Procedure.subject",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-patient"]
      }]
    },
    {
      "id" : "Procedure.subject.reference",
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
      "path" : "Procedure.subject.reference",
      "min" : 1,
      "mustSupport" : true
    },
    {
      "id" : "Procedure.encounter",
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
      "path" : "Procedure.encounter",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-encounter"]
      }]
    },
    {
      "id" : "Procedure.performed[x]",
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
      "path" : "Procedure.performed[x]",
      "min" : 1,
      "type" : [{
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
            "valueCode" : "SHOULD:able-to-populate"
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
        },
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
          "valueBoolean" : true
        }],
        "code" : "dateTime"
      },
      {
        "code" : "Period"
      },
      {
        "code" : "string"
      },
      {
        "code" : "Age"
      },
      {
        "code" : "Range"
      }]
    },
    {
      "id" : "Procedure.performer.actor",
      "path" : "Procedure.performer.actor",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-patient",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-relatedperson",
        "http://hl7.org/fhir/uv/ips/StructureDefinition/Device-observer-uv-ips",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-practitioner",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-practitionerrole",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-organization"]
      }]
    },
    {
      "id" : "Procedure.performer.onBehalfOf",
      "path" : "Procedure.performer.onBehalfOf",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-organization"]
      }]
    },
    {
      "id" : "Procedure.reasonCode",
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
      "path" : "Procedure.reasonCode",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Procedure.reasonReference",
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
      "path" : "Procedure.reasonReference",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-condition",
        "http://hl7.org/fhir/StructureDefinition/Observation",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-procedure",
        "http://hl7.org/fhir/StructureDefinition/DocumentReference"]
      }]
    }]
  }
}

```
