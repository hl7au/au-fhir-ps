A system declaring conformance to AU Patient Summary (AU PS) **SHALL** implement the conformance requirements as defined for one or both of the following actors:

- [AU PS Consumer](ActorDefinition-au-ps-actor-consumer.html)
- [AU PS Producer](ActorDefinition-au-ps-actor-producer.html)

AU PS does not define any FHIR-specific interactions and therefore does not include a CapabilityStatement.

Systems implementing AU PS **MAY** implement interactions defined in other CapabilityStatements, for example:
- [IPS Server Capability Statement](https://build.fhir.org/ig/HL7/fhir-ips/CapabilityStatement-ips-server.html)
- [International Patient Access Server CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-server.html)
- [International Patient Access Client CapabilityStatement](https://hl7.org/fhir/uv/ipa/CapabilityStatement-ipa-client.html)


### FHIR Server CapabilityStatement

Servers that implement support for AU PS profiles, declare conformance to each profile by hosting a [CapabilityStatement](http://hl7.org/fhir/capabilitystatement.html) resource at [server-base-url]/metadata that is available to both authenticated and unauthenticated clients. The capability statement declares support for a resource as either a base profile using [CapabilityStatement.rest.resource.profile](http://hl7.org/fhir/capabilitystatement-definitions.html#CapabilityStatement.rest.resource.profile) or supported profile using [CapabilityStatement.rest.resource.supportedProfile](http://hl7.org/fhir/capabilitystatement-definitions.html#CapabilityStatement.rest.resource.supportedProfile).

Example: CapabilityStatement resource for a server supporting the AU PS Patient profile as a system-wide profile that is applied across all instances of the Patient resource:

    ```
    {
      "resourceType": "CapabilityStatement",
      ...
      "rest": [
        {
          "mode": "server",
        ...
            "resource": [
              ...
              {
                "type": "Patient",
                "profile": [
                  "http://hl7.org/fhir/ps/StructureDefinition/au-ps-patient"
                ],
                ...
              }
            ]
        }
      ] 
    }
    ```

Example: CapabilityStatement resource for a server supporting the AU PS Patient profile as a profile for supported use cases provided by the server:

    ```
    {
      "resourceType": "CapabilityStatement",
      ...
      "rest": [
        {
          "mode": "server",
        ...
            "resource": [
              ...
              {
                "type": "Patient",
                "supportedProfile": [
                  "http://hl7.org.au/fhir/ps/StructureDefinition/au-ps-patient"
                ],
                ...
              }
            ]
        }
      ] 
    }
    ```