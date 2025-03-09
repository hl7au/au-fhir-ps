This version of the AU Patient Summary (AU PS) complies with [Version 1.0 of the HL7 Australia FHIR Work Group AU Variance Requirements](https://hl7.org.au/fhir/HL7%20AU%20Variance%20Requirements%20v1.0.pdf).

HL7 Australia published FHIR implementation guides are required to follow specific publishing requirements:
- **SHOULD** use AU Core profiles
- **SHOULD** use AU Base profiles and extensions
- **SHALL** include an AU Variance Statement page


### Variance from AU Base
This implementation guide has no variance (i.e. fully compliant) from AU Base FHIR Implementation Guide version 5.1.0-ci-build ([current](https://build.fhir.org/ig/hl7au/au-fhir-base/)).

Note that while there is no variance, this implementation guide imposes requirements additional to AU Bae.

#### Additionally Profiled Resources

This implementation guide profiles the following resources that are not profiled in AU Base:

- [AU PS Bundle](StructureDefinition-au-ps-bundle.html) profiles FHIR resource [Bundle](http://hl7.org/fhir/R4/bundle.html)


### Variance from AU Core
This implementation guide has no variance (i.e. fully compliant) from AU Core FHIR Implementation Guide version 1.1.0-ci-build ([current](https://build.fhir.org/ig/hl7au/au-fhir-core/)). 

Note that while there is no variance, this implementation guide imposes requirements additional to AU Core.

#### Additionally Profiled Resources

This implementation guide profiles the following resources that are not profiled in AU Core:

- [AU PS Bundle](StructureDefinition-au-ps-bundle.html) profiles FHIR resource [Bundle](http://hl7.org/fhir/R4/bundle.html)
- [AU PS Composition](StructureDefinition-au-ps-composition.html) profiles FHIR resource [Composition](http://hl7.org/fhir/R4/composition.html)


### Variance from IPS
This implementation guide has no variance (i.e. fully compliant) from IPS Implementation Guide version 2.0.0-ci-build ([current](https://build.fhir.org/ig/HL7/fhir-ips)).

Note that while there is no variance, this implementation guide imposes requirements additional to IPS.

#### Additionally Profiled Resources

This implementation guide profiles the following resources that are not profiled in IPS:

- [AU PS Encounter](StructureDefinition-au-ps-encounter.html) profiles FHIR resource [Encounter](http://hl7.org/fhir/R4/encounter.html)
- [AU PS RelatedPerson](StructureDefinition-au-ps-relatedperson.html) profiles FHIR resource [RelatedPerson](http://hl7.org/fhir/R4/relatedperson.html)
