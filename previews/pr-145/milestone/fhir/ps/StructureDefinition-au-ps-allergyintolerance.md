# AU PS AllergyIntolerance - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* [**Artefacts Summary**](artifacts.md)
* **AU PS AllergyIntolerance**

## Resource Profile: AU PS AllergyIntolerance 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-allergyintolerance | *Version*:1.0.0-ci-build | |
| * Standards status: *[Draft](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels): 2 | *Computable Name*:AUPSAllergyIntolerance |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved. | | |

 
This profile sets minimum expectations for an AllergyIntolerance resource in the context of a patient summary in an Australian context. It is based on the [AU Core AllergyIntolerance](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html) profile, and applies the additional requirements from [AllergyIntolerance (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/AllergyIntolerance-uv-ips). 

See [Comparison With Other National and International IGs](comparison.md) for a comparison between AU Patient Summary (AU PS) profiles and profiles in other implementation guides.

### Profile Specific Implementation Guidance

* See the [guidance on implementing the AllergyIntolerance resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html#profile-specific-implementation-guidance) in AU Core.

The additional obligation on `AllergyIntolerance.onsetDateTime` for [AU PS Producer](ActorDefinition-au-ps-actor-producer.md) is [SHOULD:able-to-populate](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58able-to-populate). This obligation is in addition to the obligation of [SHALL:populate-if-known](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58populate-if-known). There is no additional obligation for [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.md), the obligations of [SHALL:handle](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHALL.58handle) and [SHOULD:display](https://hl7.org/fhir/extensions/CodeSystem-obligation.html#obligation-SHOULD.58display) apply.

This additional obligation is present in the underlying structure but due to a tooling limitation is not currently rendered in the Formal Views of Profile Content. See [Zulip discussion](https://chat.fhir.org/#narrow/channel/179252-IG-creation/topic/Obligation.20Extension.20on.20ElementDefinition.2Etype.20not.20rendering) for more information.

**Examples for this Profile**: [Bundle/aups-basicsummary](Bundle-aups-basicsummary.md), [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.md), [Bundle/aups-noknownx](Bundle-aups-noknownx.md), [Bundle/aups-referral-endoconsult-autogen](Bundle-aups-referral-endoconsult-autogen.md) and [Bundle/aups-referral-endoconsult-curated](Bundle-aups-referral-endoconsult-curated.md)

**Usages:**

* Use this Profile: [AU PS Bundle](StructureDefinition-au-ps-bundle.md)
* Refer to this Profile: [AU PS Composition](StructureDefinition-au-ps-composition.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/hl7.fhir.au.ps|current/StructureDefinition/StructureDefinition-au-ps-allergyintolerance.json)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-au-ps-allergyintolerance.csv), [Excel](StructureDefinition-au-ps-allergyintolerance.xlsx), [Schematron](StructureDefinition-au-ps-allergyintolerance.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "au-ps-allergyintolerance",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 2
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-compliesWithProfile",
    "valueCanonical" : "http://hl7.org/fhir/uv/ips/StructureDefinition/AllergyIntolerance-uv-ips"
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
  "url" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-allergyintolerance",
  "version" : "1.0.0-ci-build",
  "name" : "AUPSAllergyIntolerance",
  "title" : "AU PS AllergyIntolerance",
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
  "description" : "This profile sets minimum expectations for an AllergyIntolerance resource in the context of a patient summary in an Australian context. It is based on the [AU Core AllergyIntolerance](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-allergyintolerance.html) profile, and applies the additional requirements from [AllergyIntolerance (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/AllergyIntolerance-uv-ips).",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "AU"
    }]
  }],
  "copyright" : "Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved.",
  "fhirVersion" : "4.0.1",
  "mapping" : [{
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
  "type" : "AllergyIntolerance",
  "baseDefinition" : "http://hl7.org.au/fhir/core/StructureDefinition/au-core-allergyintolerance",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "AllergyIntolerance",
      "path" : "AllergyIntolerance"
    },
    {
      "id" : "AllergyIntolerance.clinicalStatus",
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
      "path" : "AllergyIntolerance.clinicalStatus",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "AllergyIntolerance.verificationStatus",
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
      "path" : "AllergyIntolerance.verificationStatus",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "AllergyIntolerance.type",
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
      "path" : "AllergyIntolerance.type",
      "mustSupport" : true
    },
    {
      "id" : "AllergyIntolerance.code",
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
      "path" : "AllergyIntolerance.code",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "AllergyIntolerance.patient",
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
      "path" : "AllergyIntolerance.patient",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-patient"]
      }]
    },
    {
      "id" : "AllergyIntolerance.patient.reference",
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
      "path" : "AllergyIntolerance.patient.reference",
      "min" : 1,
      "mustSupport" : true
    },
    {
      "id" : "AllergyIntolerance.onset[x]",
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
      "path" : "AllergyIntolerance.onset[x]",
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
        }],
        "code" : "dateTime"
      },
      {
        "code" : "Age"
      },
      {
        "code" : "Period"
      },
      {
        "code" : "Range"
      }]
    },
    {
      "id" : "AllergyIntolerance.note",
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
      "path" : "AllergyIntolerance.note"
    },
    {
      "id" : "AllergyIntolerance.reaction",
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
      "path" : "AllergyIntolerance.reaction"
    },
    {
      "id" : "AllergyIntolerance.reaction.manifestation",
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
      "path" : "AllergyIntolerance.reaction.manifestation",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "AllergyIntolerance.reaction.severity",
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
      "path" : "AllergyIntolerance.reaction.severity"
    }]
  }
}

```
