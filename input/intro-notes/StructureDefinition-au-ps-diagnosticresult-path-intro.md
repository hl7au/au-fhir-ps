{% include comparison-note-boilerplate.md %}

### Profile specific implementation guidance
- See the [guidance on implementing the pathology result Observation resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-diagnosticresult-path.html#profile-specific-implementation-guidance) in AU Core.
- When implementing support for specimen information, the conformance expectations of the [Specimen (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Specimen-uv-ips) profile **SHALL** be met.

<div class="stu-note" markdown="1">
There is a current tool limitation that prevents the Observation.specimen element referencing the intended target profile: [Specimen (IPS)](http://hl7.org/fhir/uv/ips/StructureDefinition/Specimen-uv-ips).
</div><!-- stu-note -->
