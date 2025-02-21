02202505091 FDA Cybersecurity Premarket Condensed

*Based on the 2023 guidance:* https://www.fda.gov/regulatory-information/search-fda-guidance-documents/cybersecurity-medical-devices-quality-system-considerations-and-content-premarket-submissions

*and... we should probably incorporate the 'select updates' in here as well.*

*Really the main issue with the guidance is that the information is scattered all over. Note that for (non-binding) compliance purposes, my paraphrasing and reduction is not suitable, and you should reference the official guidance.*

*I didn't write down the details on architecture views, security controls, and the other stuff toward the back because it's much more straightforward / organized / prescriptive. It is essential reference material.*

## Intro section
* Follow your existing QMS processes if applicable, this guidance isn't meant to replace them. Stuff you're already doing in your QMS can help you as supporting evidence that you're meeting your cybersecurity obligations as manufacturer in the submission.
* Cybersecurity is part of design and supplier controls.
* Extent of cybersecurity design & documentation scales with device risk, and needs to consider the intended & actual use environments device will see. As a lower bound example, for a non-connected thermometer:
	* A limited security architecture (just device hardware and software)
	* A few security controls based on specific device design / technology
* Effectiveness of controls may diminish over time.
	* 510(k)'s be wary about directly leveraging old security controls. FDA will consider security controls as part of substantial equivalence *but not really sure how zactly.*
* The use of an SPDF is recommended as a risk control/mitigation for cybersecurity risks with impact to safety/effectiveness.
*
* 

---
**Stuff that doesn't fit anywhere**
* In premarket submission, need to identify all known vulnerabilities for the device and its components and describe for each...
	* How it was identified
	* A safety and security risk assessment including both system and device impacts
	* Details of safety/security controls taken to address the vulnerability


**What is a SPDF/SSDF?**
FDA: Secure Product Development Framework
NIST: Secure Software Development Framework

* These are development processes intended to reduce the number / severity of vulnerabilities in the product / lifecycle. Both FDA and NIST recommend adopting a S(X)DF. There are many such frameworks, including medical device-specific frameworks.
* As always, FDA notes that the SPDF may be *one way* to satisfy the QS regulation but other approaches may be taken. (*Of course any other approach needs to provide equivalent assurance based on objective evidence. It's like of like "the standard is optional.." The standard isn't really optional unless you have an expert in that field who knows every sharp edge of the alternate approach. Just follow an SPDF.*)
	* Alternate approaches (*to a SPDF? or are these alternate SPDFs?*) such as 'Medical Device and Health IT Joint Security Plan (JSP)' or IEC 81001-5-1 may be used if justified.
	* There are also frameworks from outside med device, eg ANSI/ISA 62443-4-1 from industrial automation.
* SPDF is intended to cover the entire TPLC ('Total Product Life Cycle'), ie addresses development, release, support and decommissioning.

Note that the FDA guidance does not describe a complete SPDF. The elements primarily discussed here are...
* Security Risk Management...
	* Threat Modeling
	* Cybersecurity Risk Assessment
	* Interoperability Risks
	* Risks associated with Third Party Components
	* Security Assessment of Unresolved Anomalies
* Security Architecture
* Cybersecurity Testing

**Security Architecture and Design**
* Must be able to provide a description to FDA of how each of these security objectives has been addressed by / integrated into the design...
	* Authenticity / integrity
	* Authorization
	* Availability
	* Confidentiality
	* Secure & timely updatability / patchability
* The extent of controls needed is risk-based.
	* Note that this is a cybersecurity-specific risk level and is separate from any device classification (*eg class IIb*) or level of risk/concern *a la* FDA software guidance.

**Transparency & Labelling**
* Cybersecurity information should be provided to end users...
	* What are the communication interfaces?
	* What 3rd party software is included?
	* Are there known but not disclosed vulnerabilites / risks?
	* Sufficient information to user on how to configure / update the device so that they can manage and protect the device and system.
	*(Note that the information about communication interfaces / 3rd party is relevant to hospitals who will be handed a piece of equipment that they are now responsible for managing the security of. Less relevant but not irrelevant in context of company representatives or patients.*
* Undisclosed, incorrectly identified, or incorrectly responded-to cybersecurity threats could compromise device safety/effectiveness.
* **!!** Inadequate cybersecurity *labelling* can cause a device to be considered misbranded. **!!** *(That's a spicy FDA term for your labelling not meeting regulation.)*

**Cybersecurity risk assessment**
* Cybersecurity risk assessments typically performed at system level looking at residual risk of vulnerabilities to data and device safety/effectiveness.
* Cybersecurity risk =/= patient risk.
	* Security risk assessment process is separate from safety risk assessment / 14971 because the scope of harm / assessment factors are different.
	* FDA recommends having separate safety and security assessments.
* Cybersecurity risks may be intentional or unintentional, which makes it difficult / impossible to use historical data to do a probabilistic occurrence estimate the way we do with safety assessment. Instead the focus is on exploitability
	* (This is another reason it's recommended to have separate security & safety assessments.)
	* Note that exploitability factors can be different premarket vs postmarket.
* Risk transfer := some action to mitigate risk that ends up shifting the risk onto somebody else. (?)
	* If transferring risks to users, need to assess (a) whether it's appropriate and (b) inform them about the risks, including supply chain risks and end of life.
	* What risks will be transferred to the patient at the end of system life? How (if) they will be able to take on that role?
* Should address interoperability with...
	* Other medical devices (if applicable)
	* Other (non-device) functions *(in the 'multiple device functions' guidance sense)*
	* General-purpose computer platforms
* Should assess impact of communication technology / protocol itself having a vulnerability... are additional controls beneath (*on top of?*) that layer warranted?
*  Security risk management process is required throughout TPLC - risk documentation should be fed with new threats, vulnerabilities, assets or adverse impacts as discovered or as things change. (Supports/feeds CAPA)
* Risk assessments should account for different configurations in use in the field that might have different risk profiles. ie, if there are multiple versions, we should assess each / the diff to ensure patient risks are fully assessed.

**Summary of security risk report components:**
* Threat modeling documentation
* Cybersecurity risk assessment
* SBOM
* Component support info
* Vulnerability assessments
* Unresolved anomaly assessments
* Summary of risk evaluation methods / processes
* Residual risk assessment from security assessment
* Risk mitigation activities taken
* And traceability between...
	* The threat model
	* Cybersecurity risk assessment
	* SBOM
	* Testing documentation

**What is threat modeling?**
{Security objectives, risks, vulnerabilities} --> {Countermeasures to prevent, monitor or respond to threats}
* States assumptions about environment of use
  eg hospital network is inherently hostile and an adversary could alter/drop/replay packets.
* Captures cybersecurity risks from... (*and looking particularly for things that would be overlooked in a traditional safety risk assessment.*)
	* supply chain
	* manufacturing deployment
	* interoperation with other devices
	* maintenance / update activities
	* decommissioning
* Various approaches to threat modeling, should be able to rationalize approach taken.
* Threat modeling might be performed at design reviews.
* Threat modeling documentation should review the security features of the device in context of system safety & effectiveness.

**Evaluation of Third Party Components**
See additional guidance docs for further information on use of / evaluation of thidr party components...
(1) https://www.fda.gov/regulatory-information/search-fda-guidance-documents/shelf-software-use-medical-devices
(2) https://www.fda.gov/regulatory-information/search-fda-guidance-documents/cybersecurity-networked-medical-devices-containing-shelf-ots-software

* Manufacturer Obligations: To support design controls (820.30(g)) and supply chain / purchasing risk (820.50) obligations, all software, whether developed by the manufacturer or a third party, should be assessed for cybersecurity risk.
	* (Legal manufacturer is responsible to ensure all purchased or otherwise received product/services meet their specifications/requirements.)
	* Resulting evaluations / documentation should be included in the DMR  and DHF.
* End of Life: 
	* Submission should include plans for how third party software components could be replaced if upstream support ends or some issue arises.
	* Need to provide users with any info they need to manage risks with the software components - known vulnerabilities, configuration details, any relevant risk/security information.
* SBOM supports evaluation of third-party components and must be provided to FDA. (Also must be provided to ISO 27001 auditor?) See [[09102405251 Software BOM (SBOM)]]

**Security Assessment of Unresolved Anomalies**
* Software premarket guidance asks for a list of bugs that exist in the product at the time of submission and to evaluate the impact of each on safety/effectiveness. However, these bugs could also be potential vulnerabilities, so we should also perofmr a security assessment including whether any Common Weakness Enumeration categories are present.

**Reporting and Metrics**
* Part 806 may be needed for certain postmarket vulnerabilities - see Postmarket Cybersecurity Guidance
* Metrics: FDA recommends tracking and recording the metrics below and providing them in premarket submissions and PMA annual reports when available:
	* (Note that for initial submission with no predicate the data might not be available but we should include it in our risk management plan and SPDF.)
	* (1) Percentage of identified vulnerabilities that are patched or updated (defect density)
	* (2) Duration from vulnerability identification to when it is updated or patched
	* (3) Duration from when an update or patch is available to complete implementation in devices deployed in the field, to the extent known
