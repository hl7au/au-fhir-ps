# Resource au-ps-actor-consumer



## Resource Content

```json
{
  "resourceType" : "Basic",
  "id" : "au-ps-actor-consumer",
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
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.url",
    "valueUri" : "http://hl7.org.au/fhir/ps/ActorDefinition/au-ps-actor-consumer"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.version",
    "valueString" : "1.0.0-ci-build"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.name",
    "valueString" : "AUPSConsumer"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.title",
    "valueString" : "AU PS Consumer"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.status",
    "valueCode" : "active"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.date",
    "valueDateTime" : "2026-06-19T08:07:30+00:00"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.publisher",
    "valueString" : "HL7 Australia"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.contact",
    "valueContactDetail" : {
      "name" : "HL7 Australia FHIR Work Group",
      "telecom" : [{
        "system" : "url",
        "value" : "https://confluence.hl7.org/display/HAFWG",
        "use" : "work"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.description",
    "valueMarkdown" : "An AU PS Consumer is a system that consumes an AU PS Bundle and uses it to display or process patient summary content. This actor is based on the Consumer (IPS) actor, and describes the additional requirements and documentation applied for the Australian context."
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.jurisdiction",
    "valueCodeableConcept" : {
      "coding" : [{
        "system" : "urn:iso:std:iso:3166",
        "code" : "AU"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.copyright",
    "valueMarkdown" : "Used by permission of HL7 International, all rights reserved Creative Commons License. HL7 Australia© 2024+; Licensed Under Creative Commons No Rights Reserved."
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.type",
    "valueCode" : "system"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.documentation",
    "valueMarkdown" : "An AU PS Consumer **SHALL** comply with the requirements of the [Consumer (IPS)](https://hl7.org/fhir/uv/ips/STU2/ActorDefinition-Consumer.html), and:\n\n - **SHALL** implement the AU PS Bundle, AU PS Composition and AU PS Patient profiles\n\n - **SHALL** for each mandatory section in AU PS Composition, implement the AU PS profiles referenced by the section entry (i.e. AU PS AllergyIntolerance, AU PS Condition, AU PS MedicationStatement and AU PS MedicationRequest)\n\n - **SHALL** for each recommended section in AU PS Composition, implement the profiles referenced by the section entry (e.g. AU PS Immunization, Observation Results - Radiology (IPS), AU PS Procedure, and DeviceUseStatement (IPS))\n\n - **SHALL** implement the AU PS Consumer obligations in the implemented profiles. Where an IPS profile is referenced in the AU PS Bundle the obligations of the Consumer (IPS) actor **SHALL** apply\n\n - **SHALL** consume resources with *Must Support* elements populated in accordance with the requirements for [Missing Data, Empty Sections, Known Absence of Data, No Known X](general-requirements.html#missing-data-empty-sections-known-absence-of-data-no-known-x) or [Suppressed Data](general-requirements.html#suppressed-data)\n\n"
  },
  {
    "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-ActorDefinition.derivedFrom",
    "valueCanonical" : "http://hl7.org/fhir/uv/ips/ActorDefinition/Consumer"
  }],
  "code" : {
    "coding" : [{
      "system" : "http://hl7.org/fhir/fhir-types",
      "code" : "ActorDefinition"
    }]
  }
}

```
