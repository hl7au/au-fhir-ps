# AU PS Encounter - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* [**Artefacts Summary**](artifacts.md)
* **AU PS Encounter**

## Resource Profile: AU PS Encounter 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-encounter | *Version*:1.0.0-ci-build | |
| * Standards status: *[Draft](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels): 2 | *Computable Name*:AUPSEncounter |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved. | | |

 
This profile sets minimum expectations for an Encounter resource in the context of a patient summary in an Australian context. It is based on the [AU Core Encounter](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-encounter.html) profile, and applies the additional constraints for use in a patient summary context consistent with the profiling conventions of [IPS](https://hl7.org/fhir/uv/ips/STU2/). 

See [Comparison With Other National and International IGs](comparison.md) for a comparison between AU Patient Summary (AU PS) profiles and profiles in other implementation guides.

### Profile Specific Implementation Guidance

* See the [guidance on implementing the Encounter resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-encounter.html#profile-specific-implementation-guidance) in AU Core.
* The Encounter resource can represent a clinical indication with `Encounter.reasonCode`, or a reference with `Encounter.reasonReference` to a Condition or other resource. 
* Although both are marked as **Must Support**, producers are not required to support both a code and a reference, but they **SHALL** support **at least one** of these elements
* A consumer **SHALL** support both elements
 

**Examples for this Profile**: [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.md)

**Usages:**

* Use this Profile: [AU PS Bundle](StructureDefinition-au-ps-bundle.md)
* Refer to this Profile: [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.md) and [AU PS Procedure](StructureDefinition-au-ps-procedure.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/hl7.fhir.au.ps|current/StructureDefinition/StructureDefinition-au-ps-encounter.json)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-au-ps-encounter.csv), [Excel](StructureDefinition-au-ps-encounter.xlsx), [Schematron](StructureDefinition-au-ps-encounter.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "au-ps-encounter",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 2
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
  "url" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-encounter",
  "version" : "1.0.0-ci-build",
  "name" : "AUPSEncounter",
  "title" : "AU PS Encounter",
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
  "description" : "This profile sets minimum expectations for an Encounter resource in the context of a patient summary in an Australian context. It is based on the [AU Core Encounter](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-encounter.html) profile, and applies the additional constraints for use in a patient summary context consistent with the profiling conventions of [IPS](https://hl7.org/fhir/uv/ips/STU2/).",
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
  "type" : "Encounter",
  "baseDefinition" : "http://hl7.org.au/fhir/core/StructureDefinition/au-core-encounter",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Encounter",
      "path" : "Encounter"
    },
    {
      "id" : "Encounter.status",
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
      "path" : "Encounter.status"
    },
    {
      "id" : "Encounter.class",
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
      "path" : "Encounter.class"
    },
    {
      "id" : "Encounter.serviceType",
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
      "path" : "Encounter.serviceType",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Encounter.subject",
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
      "path" : "Encounter.subject",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-patient"]
      }]
    },
    {
      "id" : "Encounter.participant",
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
      "path" : "Encounter.participant"
    },
    {
      "id" : "Encounter.participant.type",
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
      "path" : "Encounter.participant.type",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Encounter.participant.individual",
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
      "path" : "Encounter.participant.individual",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-practitioner",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-practitionerrole",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-relatedperson"]
      }]
    },
    {
      "id" : "Encounter.period",
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
      "path" : "Encounter.period"
    },
    {
      "id" : "Encounter.reasonCode",
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
      "path" : "Encounter.reasonCode",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Encounter.reasonReference",
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
      "path" : "Encounter.reasonReference",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-condition",
        "http://hl7.org/fhir/StructureDefinition/Observation",
        "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-procedure"]
      }]
    },
    {
      "id" : "Encounter.location",
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
      "path" : "Encounter.location"
    },
    {
      "id" : "Encounter.location.location",
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
      "path" : "Encounter.location.location"
    },
    {
      "id" : "Encounter.serviceProvider",
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
      "path" : "Encounter.serviceProvider",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-organization"]
      }]
    }]
  }
}

```
