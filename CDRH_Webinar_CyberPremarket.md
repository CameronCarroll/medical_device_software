10022405341 RN FDA CDRH Webinar Cybersecurity 2023 Guidance

https://www.youtube.com/watch?v=mQlD7jYWjOY

2023 guidance supersedes 2014 guidance on content of PMA for cybersecurity.

There are specific labelling requirements in the guidance.

**Recommended resource for SBOM?**
Framing Software Component Transparency: Establishing a Common Software Bill of Material (SBOM) is the guidance document expected by FDA.

**How is SBOM actually disclosed to FDA?**
Vulns associated with third party software components, that are just coming out of the development process, these can be part of device submission in cybersecurity risk management
(Assessment of vulnerabilities for third party software components)

Postmarket - Need to have a plan for coordinated vulnerability disclosure / related processes. (Disclosed coordinated with CISA and any with FDA if it's an uncontrolled vulnerability.)

**Cybersecurity Management Plan**
To what extent do we need to document personnel responsible?
--> Looking for personnel with particular roles and responsibilities in postmarket lifecycle - maybe identify roles within product team or postmarket team that have responsibilities that are identified in the management plan, to assure there are resources / management / accountability for those activities.
But not individual staff names or number of people. Just need to demonstrate we have people in the org who will be carrying out that work.

**Sharing SBOMs with users?**
Labels should be 'inclusive' but only may include SBOMs. (?? Language in guidance?)
Do SBOMs need to be provided to customers?

--> Guidance recommends SBOMs are included as part of the labelling and should be available to the end users to hlep them understand cybersecurity risk.
This is distinct from the requirement in FD&C that says SBOM needs to be part of premarket submission.

**Depth of SBOM wrt OTS software**
How to deal with OTS software where we really can't say what all the subcomponents are?
--> NTIA framing document discusses depth
Recommendation from FDA - SBOMs are complete - Have all transitive dependencies included (as stated in guidance)
If MFG doesn't know all the transitive dependency information, then need to justify why the information is not present.

**To what extent do we need to justify method of threat analysis used?**
FDA looking for us to describe what methodology was used and the reasons why it's applicable / appropriate for our system / based on design considerations / appropriately capture all the threats system will be exposed to and we've applied an appropriate scoring methodology to determine if risk mitigations have reduced risk to an acceptable level.
(For threat modeling / cyber risk assessment there are pros/cons for the various methods.)

eg NIST 800-30 or... SWIFT??

May need to be tailed for us, may involve qualitative assessment so need to ensure it's fit for purpose for our device characteristics.

**Legacy devices...**
Expectations for testing legacy devices that don't connect to networks, but may be cyber devices.
--> FDA believes there should be recurring testing throughout the lifecycle of the device - if we are making changes and going to FDA for a modification submission, we should have all of the elements in the guidance. 
(Evolving nature of cybersecurity risk, and devices are continuing to be used/maintained, so the cybersecurity controls should be appropriate for the particular design/device.)

Even if stuff like the architecture views don't exist because the device is like 15 years old, FDA expects to see the full set of documentation.
