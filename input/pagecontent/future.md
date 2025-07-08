### AU Patient Summary (AU PS) Target Release Time frames
AU PS R1 (& AU Core R2) Target Release Timeline:
* Intermediate draft snapshots from December 2024 and for each HL7 AU Connectathon
* R1 Ballot for Comment in the August/September 2025 cycle
* R1 Ballot for Working Standard in the February/March 2026 cycle, published by June 2026
* Continued updates on a yearly / 18-monthly cycle from then on

 <div> 
    <img src="TargetTimeframes.png" alt="AU Patient Summary R1 Target Release Time Frame" style="width:75%"/>
  </div>
*Figure 1: AU PS R1 Target Release Time Frame*
<br/>

Future updates of AU PS updates would reflect changes to:
 - AUCDI (Patient summary)
 - AU Core
 - International Patient Summary
 - requests from the AU FHIR community
 
### AU PS R1 Development process
The first release of AU PS is an 18 month process from HL7 AU proposal to publication of the first release, outlined in the figure below:

 <div> 
    <img src="R1Process.png" alt="AU Patient Summary R1 Development process" style="width:100%"/>
  </div>
*Figure 2: AU PS R1 Development process*
<br/>

#### Maturing the Baseline
The approach to develop and mature AU PS is outlined below making reference to the [FHIR Maturity Level (FMM) levels](https://build.fhir.org/ig/hl7au/au-fhir-base/generalguidance.html#maturity-levels) is shown in the figure below.

 <div> 
    <img src="maturing.png" alt="Maturing the AU Patient Summary baseline" style="width:80%"/>
  </div>
*Figure 3: Maturing the AU PS baseline*
<br/>

### Future Candidate Requirements Under Consideration
The following items are under consideration to add to AU PS.

* **Last Updated**: AUCDI element Last Updated is intended to reflect when a data group was last updated, capturing clinical relevance and currency. A known and implemented solution in other jurisdictions for similar requirements is the use of the Provenance resource. An alternative to the use of Provenance may be the definition of custom extensions. Future versions of AU Core will develop and test approaches to addressing Last Updated. When defined in AU Core, it will be inherited by AU PS.
* **DocumentReference Profile**: Future versions of AU Core will develop and test an AU Core DocumentReference profile to support sharing of clinical notes across multiple use cases to support common implementation. When defined in AU Core, 
* **Device Profiles**: Use of the Device resource for medical devices, and devices that perform, observe, or author clinical data, are required to support multiple downstream use cases including eRequesting and patient summary. Future versions of AU Core will develop and test profiles to support common implementation of Device information. A potential outcome of this work in AU Core is either a new AU PS profiles or direct reference to the defined AU Core profile.
* **Additional Diagnostic Results Profiles**: Additional AU Core profiles to support common implementation of additional aspects of diagnostic results including imaging, specimen, and reports are expected to be developed and tested in future versions of AU Core. A potential outcome of this work in AU Core are additional AU PS profiles that describe how to comply with the AU Core and IPS requirements: AU PS Imaging Result Observation, AU PS ImagingStudy, AU PS Specimen, and AU PS DiagnosticReport.
* **Pregnancy Information Profiles**: Exchange of pregnancy information is supported in AU PS via reference to IPS profiles. Additional AU Core profiles to support common implementation of widely shared pregnancy information including pregnancy assertion (sometimes referred to as pregnancy status), last menstrual period and estimated date of delivery are under consideration for a future release may be developed and tested in future versions of AU Core. A potential outcome of this work in AU Core are additional AU PS profiles that describe how to comply with the AU Core and IPS requirements: AU PS Pregnancy Status and AU PS Pregnancy EDD.
