### Security and Privacy

When implementing AU PS, implementers need to be aware of [FHIR security considerations](https://hl7.org/fhir/R4/security.html) and implement measures to protect information privacy and prevent exploitation by malicious actors.

Those implementing AU PS are also advised to review the [FHIR Implementer Safety Checklist](https://hl7.org/fhir/R4/safety.html) for important considerations in secure and safe system implementation.

Implementers are further advised to be familiar with the requirements of IPS and AU Core when implementing AU PS, in particular:
- [IPS Privacy and Security Considerations](https://build.fhir.org/ig/HL7/fhir-ips/Privacy-and-Security-Considerations.html)
- [AU Core Security and Privacy](https://build.fhir.org/ig/hl7au/au-fhir-core/security.html)

Implementers of AU PS need to be aware of their obligations regarding security, privacy, and consent in Australia.

For AU PS, specific security requirements include:
- Systems **SHOULD** conform to [FHIR Communications Security](https://hl7.org/fhir/R4/security.html#http) requirements.
- Systems **SHOULD** support [SMART App Launch](https://hl7.org/fhir/smart-app-launch/) for client authentication and authorisation.
- Systems **SHALL** use TLS version 1.2 or higher for data exchange.
- Systems **SHOULD** use TLS version 1.3 for data exchange.
- Systems **SHOULD** use the Australian Cyber Security Centre (ACSC) [TLS configuration guidelines](https://www.cyber.gov.au/resources-business-and-government/maintaining-devices-and-systems/system-hardening-and-administration/web-hardening/implementing-certificates-tls-https-and-opportunistic-tls) that include recommendations for configuring protocol features and acceptable cipher suites when implementing TLS.
