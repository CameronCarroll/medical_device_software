09102405251 Software BOM (SBOM)

# What is an SBOM?

A Software Bill of Materials (SBOM) is a nested inventory of all building blocks that make up a software product, including all open-source and third-party components present in a medical software product's codebase.

# When is SBOM required? By who?

SBOM is mandated:
- For government software by 2021 Executive Order 14028, Improving the Nation's Cybersecurity (included for historical context)
- For medical devices on US market by US Code §360n–2. Ensuring cybersecurity of devices
- For devices on EU market by EN IEC 81001-5-1
  - SBOM requirement flows in via configuration management in this standard
  - This standard is maybe a good middle ground between FDA and EU expectations
  - Recognized elsewhere in the world?

# What needs to be part of the SBOM?

## Minimum Required Elements
- Data on supplier, component name, component version, other unique identifiers
- Dependency relationship
- Author of SBOM data
- Timestamp
- Support for automation, including ability to be generated automatically and read by machines to allow for scaling across software ecosystem

## Data Formats
- SPDX
- CycloneDX
- SWID tags

## SBOM Management Practices
- Frequency
- Depth
- Known unknowns
- Distribution and delivery
- Access control
- Accommodation of mistakes

## CDRH Recommendations
CDRH recommends to:
- Provide SBOMs to FDA to facilitate understanding/evaluation of device risk
- Provide SBOMs to users to enable risk management activities

### Beyond Minimum Elements
FDA CDRH also wants:
- Known vulnerability information
- Support status / level of support
- End of support/end of life dates

EU additional requirements (per 81001-5-1):
- Status "Maintained vs Required vs Supported"
  - Maintained: Responsibility lies with the device manufacturer, who monitors for vulnerabilities and provides patches
  - Required: Responsibility lies with the operator
  - Example: A device which is Maintained goes EOL (eg windows OS is no longer supported), then the SBOM attribute for this item should be updated from "Maintained" to "Required"

*Note: Some SBOM implementations are intended more for software development than cybersecurity management. Regulators are asking for more information than is found in a typical technical SBOM.*

# How is SBOM intended to be used by manufacturers?

- Identify software items that are unsupported or will reach EOL (hopefully earlier in development lifecycle)
  - Depending on depth, this may uncover system libraries / tools that are buried deeply in the device software
- Consult regularly against vulnerability databases and assess risk of newly found risks that surface in those databases
  - This allows mitigation of risk for black box components where threat modeling cannot be performed
- They have hundreds/thousands of devices from many manufacturers, resulting in a gigantic library of SBOMs over time
- When matching against vulnerability database, names may not exactly match, so the matching algorithm/regex may need reconciliation

# How is SBOM intended to be used by FDA and other regulators?

Current understanding is limited. They intend to assess the risk of the device software before those risks are put onto the market.

# How is SBOM intended to be used by operators (hospitals)?

The goal is to prevent scenarios such as medical devices being compromised by malware that impacts network connectivity and prevents data transfer. This could happen due to:
- Lack of communication about end of life information
- Inadequate planning for equipment retirement/upgrade
- Insufficient physical security controls

Manufacturers provide operators with SBOMs to enable:
- Independent vulnerability scanning
- Replacement planning based on risk assessment of outdated devices

*Note: SBOM implementation is still new, with ongoing challenges in providing operators with actionable information. FDA released guidance/discussion in Autumn 2024 addressing SBOM interoperability and usability.*

# Determining Component End of Life (EOL)

- EOL may be difficult to determine and not readily provided by the source
- Information may need to be collected from multiple sources
- Some components may not have EOL or a roadmap

# How to Actually Create SBOM?

## Challenges
- May be more complex than just listing input ingredients
- Could include hundreds of thousands of entries across software layers
- Some suppliers may not disclose underlying component details
- Must be maintained for every software configuration
- Needs SBOMs for all configurations in the field

## Tools and Resources
- Many existing SBOM tools focus on software development rather than vulnerability management/sharing
- Medcrypt offers products for automatic SBOM generation

## Regulatory Framework
- FDA Requirements: NTIA framing document plus additional attributes from guidances
- EU Requirements: IEC 81001-5-1

# Definition from EO 14028

"Software Bill of Materials" or "SBOM" means a formal record containing the details and supply chain relationships of various components used in building software. Software developers and vendors often create products by assembling existing open source and commercial software components. The SBOM enumerates these components in a product. It is analogous to a list of ingredients on food packaging.

## SBOM Benefits
- **For Developers**: Ensure components are up to date and respond quickly to vulnerabilities
- **For Buyers**: Perform vulnerability or license analysis for risk evaluation
- **For Operators**: Quickly determine potential risk from newly discovered vulnerabilities

A machine-readable SBOM format enables automation and tool integration. SBOMs become more valuable when stored in easily queryable repositories.

# References

- NTIA "Framing Software Component Transparency: Establishing a Common Software Bill of Materials" 
  - https://ntia.gov/sites/default/files/publications/ntia_sbom_framing_2nd_edition_20211021_0.pdf
  - 2021 version referenced by FDA guidance as canonical reference
- https://csrc.nist.gov/csrc/media/Presentations/2023/fda-s-medical-device-program-and-sbom/images-media/JWilkerson-ssca-forum-053123.pdf
- "Bridging the Gap – Navigating EU and US Medical Device Cybersecurity Regulations" webinar, Nov 7 2024 (Johner Institute, Medcrypt, MedISAO)
