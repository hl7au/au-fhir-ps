# AU PS Organization - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* [**Artefacts Summary**](artifacts.md)
* **AU PS Organization**

## Resource Profile: AU PS Organization 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-organization | *Version*:1.0.0-ci-build | |
| * Standards status: *[Draft](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels): 2 | *Computable Name*:AUPSOrganization |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved. | | |

 
This profile sets minimum expectations for an Organization resource in the context of a patient summary in an Australian context. It is based on the [AU Core Organization](http://hl7.org.au/fhir/core/StructureDefinition/au-core-organization) profile, and applies the additional requirements from [Organization (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Organization-uv-ips). 

See [Comparison With Other National and International IGs](comparison.md) for a comparison between AU Patient Summary (AU PS) profiles and profiles in other implementation guides.

### Profile Specific Implementation Guidance

* See the [guidance on implementing the Organization resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-organization.html#profile-specific-implementation-guidance) in AU Core.

**Examples for this Profile**: [Bundle/aups-basicsummary](Bundle-aups-basicsummary.md), [Bundle/aups-gpvisit-retrieval](Bundle-aups-gpvisit-retrieval.md), [Bundle/aups-noknownx](Bundle-aups-noknownx.md), [Bundle/aups-referral-endoconsult-autogen](Bundle-aups-referral-endoconsult-autogen.md), [Bundle/aups-referral-endoconsult-curated](Bundle-aups-referral-endoconsult-curated.md) and [Bundle/aups-section-emptyreason](Bundle-aups-section-emptyreason.md)

**Usages:**

* Use this Profile: [AU PS Bundle](StructureDefinition-au-ps-bundle.md)
* Refer to this Profile: [AU PS Composition](StructureDefinition-au-ps-composition.md), [AU PS Pathology Result Observation](StructureDefinition-au-ps-diagnosticresult-path.md), [AU PS Encounter](StructureDefinition-au-ps-encounter.md), [AU PS MedicationRequest](StructureDefinition-au-ps-medicationrequest.md)... Show 3 more, [AU PS Patient](StructureDefinition-au-ps-patient.md), [AU PS PractitionerRole](StructureDefinition-au-ps-practitionerrole.md) and [AU PS Procedure](StructureDefinition-au-ps-procedure.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/hl7.fhir.au.ps|current/StructureDefinition/StructureDefinition-au-ps-organization.json)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-au-ps-organization.csv), [Excel](StructureDefinition-au-ps-organization.xlsx), [Schematron](StructureDefinition-au-ps-organization.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "au-ps-organization",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 2
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-compliesWithProfile",
    "valueCanonical" : "http://hl7.org/fhir/uv/ips/StructureDefinition/Organization-uv-ips"
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
  "url" : "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-organization",
  "version" : "1.0.0-ci-build",
  "name" : "AUPSOrganization",
  "title" : "AU PS Organization",
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
  "description" : "This profile sets minimum expectations for an Organization resource in the context of a patient summary in an Australian context. It is based on the [AU Core Organization](http://hl7.org.au/fhir/core/StructureDefinition/au-core-organization) profile, and applies the additional requirements from [Organization (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Organization-uv-ips).",
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
    "identity" : "servd",
    "uri" : "http://www.omg.org/spec/ServD/1.0/",
    "name" : "ServD"
  },
  {
    "identity" : "w5",
    "uri" : "http://hl7.org/fhir/fivews",
    "name" : "FiveWs Pattern Mapping"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Organization",
  "baseDefinition" : "http://hl7.org.au/fhir/core/StructureDefinition/au-core-organization",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Organization",
      "path" : "Organization"
    },
    {
      "id" : "Organization.identifier",
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
      "path" : "Organization.identifier"
    },
    {
      "id" : "Organization.identifier:hpio",
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
      "path" : "Organization.identifier",
      "sliceName" : "hpio"
    },
    {
      "id" : "Organization.identifier:abn",
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
      "path" : "Organization.identifier",
      "sliceName" : "abn"
    },
    {
      "id" : "Organization.type",
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
      "path" : "Organization.type",
      "type" : [{
        "code" : "CodeableConcept",
        "profile" : ["http://hl7.org/fhir/uv/ips/StructureDefinition/CodeableConcept-uv-ips"]
      }]
    },
    {
      "id" : "Organization.name",
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
      "path" : "Organization.name"
    },
    {
      "id" : "Organization.telecom",
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
      "path" : "Organization.telecom"
    },
    {
      "id" : "Organization.telecom.system",
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
      }],
      "path" : "Organization.telecom.system"
    },
    {
      "id" : "Organization.telecom.value",
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
      }],
      "path" : "Organization.telecom.value"
    },
    {
      "id" : "Organization.address",
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
      "path" : "Organization.address"
    }]
  }
}

```
