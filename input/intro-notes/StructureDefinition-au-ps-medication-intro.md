<div class="note-to-balloters" markdown="1">
**Upcoming NCTS ValueSet Availability**

<code>Medication.ingredient.item[x]</code> inherits preferred binding <a href="https://build.fhir.org/ig/hl7au/au-fhir-base/ValueSet-amt-mp-codes.html">AMT Medicinal Product and Substances</a> from AU Base. A request has been submitted to NCTS to publish an equivalent value set, but it is not yet available at the time of publication.

In the interim, the AU Base value set remains in use and is expected to be deprecated upon release of the NCTS value set.

Related JIRA issue with details is: <a href="https://jira.hl7.org/browse/FHIR-47076">AU Base: FHIR-47076</a>.
</div>

{% include comparison-note-boilerplate.md %}

### Profile Specific Implementation Guidance
- See the [guidance on implementing the Medication resource](https://build.fhir.org/ig/hl7au/au-fhir-core/StructureDefinition-au-core-medication.html#profile-specific-implementation-guidance) in AU Core.
- When populating `Medication.code` producers **SHALL** correctly populate `Medication.code.coding` with either a code from [Australian Medication](https://healthterminologies.gov.au/fhir/ValueSet/australian-medication-1) or [PBS Item Codes](https://build.fhir.org/ig/hl7au/au-fhir-base//ValueSet-pbs-item.html), or both, if a coded value is known and **MAY** populate with a code from another code system.
  - Producers **MAY** populate with only text if no coded value is known.
