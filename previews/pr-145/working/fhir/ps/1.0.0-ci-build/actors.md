# Actor Definitions - AU Patient Summary Implementation Guide v1.0.0-ci-build

* [**Table of Contents**](toc.md)
* [**FHIR artefacts**](artefacts.md)
* **Actor Definitions**

## Actor Definitions

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

The following actor definitions define the actor roles that a system can implement for AU Patient Summary.

* [AU PS Consumer actor](ActorDefinition-au-ps-actor-consumer.md)

An AU PS Consumer is a system that receives an AU PS Bundle and uses it to display or process patient summary content. This actor is based on the [Consumer (IPS)](https://hl7.org/fhir/uv/ips/STU2/ActorDefinition-Consumer.html) actor, and describes the additional requirements and documentation applied for the Australian context.

* [AU PS Producer actor](ActorDefinition-au-ps-actor-producer.md)

An AU PS Producer is a system that creates or assembles an AU PS Bundle through automated generation or human curation of the patient summary content. This actor is based on the [Creator (IPS)](https://hl7.org/fhir/uv/ips/STU2/ActorDefinition-Creator.html) actor, and describes the additional requirements and documentation applied for the Australian context.

