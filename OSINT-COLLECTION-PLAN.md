# OSINT Collection Plan Framework

## Overview

This document provides a structured framework for OSINT (Open-Source Intelligence) collection planning. It helps practitioners organize intelligence gathering activities systematically and efficiently across multiple operational domains.

## Intelligence Cycle

The intelligence cycle is a continuous process that guides information collection, analysis, and dissemination:

1. **Planning & Direction** - Define intelligence requirements and objectives
2. **Collection** - Gather information from open sources
3. **Processing** - Convert raw data into a usable format
4. **Analysis & Production** - Evaluate and interpret information
5. **Dissemination** - Deliver intelligence products to stakeholders
6. **Feedback** - Review and refine the process

## Intelligence Requirements Model (CIR/CIN/PIR/EEI/MES/HVA)

This section defines the hierarchical intelligence requirements framework used to structure and prioritize OSINT collection efforts. Understanding this model ensures that collection activities remain aligned with organizational objectives and stakeholder needs.

### Definitions

#### Stakeholder Critical Intelligence Requirements (CIRs)
**Critical Intelligence Requirements (CIRs)** are the highest-level intelligence needs expressed by decision-makers and stakeholders. They represent the fundamental questions that leadership needs answered to make informed strategic decisions.

- **Characteristics:**
  - Directly tied to organizational mission and objectives
  - Expressed in business or operational language
  - Rarely change unless mission changes
  - Typically 3-7 per organization/operation

- **Example CIRs:**
  - "What are the active threats to our critical infrastructure?"
  - "Which adversary groups are targeting our sector?"
  - "What vulnerabilities exist in our supply chain?"

#### Critical Intelligence Needs (CINs)
**Critical Intelligence Needs (CINs)** break down CIRs into more specific intelligence areas. They translate strategic requirements into tactical intelligence domains.

- **Characteristics:**
  - Derived directly from CIRs
  - More specific than CIRs but still broad
  - Focus on particular threat domains or asset categories
  - Multiple CINs may support a single CIR

- **Example CINs:**
  - "Threat actor TTPs targeting OT systems"
  - "Vulnerabilities in edge computing infrastructure"
  - "Third-party vendor security posture"

#### Priority Intelligence Requirements (PIRs)
**Priority Intelligence Requirements (PIRs)** are specific, actionable intelligence questions that directly support CINs. They represent the concrete questions that intelligence collectors and analysts work to answer.

- **Characteristics:**
  - Specific and measurable
  - Time-bound when appropriate
  - Directly answerable through collection activities
  - Multiple PIRs support each CIN

- **Example PIRs:**
  - "Which APT groups have demonstrated capability to compromise industrial control systems in the last 12 months?"
  - "What zero-day vulnerabilities affecting our edge devices have been disclosed in the past 90 days?"
  - "Which of our vendors have experienced data breaches in the past year?"

#### Essential Elements of Information (EEIs)
**Essential Elements of Information (EEIs)** are the specific data points, indicators, or facts needed to answer PIRs. They represent the granular information that collectors actively seek.

- **Characteristics:**
  - Highly specific and tactical
  - Observable or discoverable through OSINT
  - Directly maps to collection sources and methods
  - Multiple EEIs combine to answer a single PIR

- **Example EEIs:**
  - "IP addresses associated with APT28 infrastructure"
  - "CVE identifiers for vulnerabilities in Cisco edge routers"
  - "Breach notification filings by vendor companies"
  - "Social media posts by known threat actors"
  - "GitHub repositories containing exploitation code"

#### Mission Essential Systems (MES)
**Mission Essential Systems (MES)** are the IT/OT systems, networks, and technologies that are critical to organizational operations. Understanding MES helps prioritize intelligence collection efforts.

- **Characteristics:**
  - Systems whose failure would severely impact mission
  - Include both IT and OT/ICS environments
  - Span physical and digital infrastructure
  - Require tailored threat intelligence

- **Example MES:**
  - SCADA systems controlling power distribution
  - Aviation traffic control systems
  - Telecommunications network backbone
  - Cloud-based identity management platforms
  - AI/ML production systems
  - Edge computing infrastructure

#### High Value Assets (HVAs)
**High Value Assets (HVAs)** are specific resources, data, or capabilities that adversaries are most likely to target and whose compromise would cause significant damage.

- **Characteristics:**
  - Most attractive targets for adversaries
  - Highest consequence if compromised
  - May be systems, data, or individuals
  - Drive defensive priorities

- **Example HVAs:**
  - Customer personally identifiable information (PII) databases
  - Intellectual property repositories
  - Administrative credentials and privileged accounts
  - Critical network infrastructure devices
  - Key personnel with access to sensitive information
  - Certificate authorities and signing keys

### Intelligence Requirements Hierarchy: Example Mapping

The following table demonstrates how intelligence requirements flow from strategic to tactical levels, with explicit references to MES and HVAs:

| **CIR** | **CIN** | **PIR** | **EEI** | **Related MES** | **Related HVA** |
|---------|---------|---------|---------|-----------------|-----------------|
| What are the active cyber threats to our telecommunications infrastructure? | Nation-state actors targeting telecom backbone systems | Which APT groups have demonstrated capability to compromise 5G core network elements in the past 6 months? | • Known APT group names and aliases<br>• IOCs (IPs, domains, hashes)<br>• TTPs specific to 5G attacks<br>• Tool names and repositories<br>• Public threat reports mentioning 5G | • 5G Core network<br>• Network slicing infrastructure<br>• Mobile edge computing | • Subscriber data databases<br>• Network configuration data<br>• Cryptographic keys<br>• Administrative access systems |
| What vulnerabilities threaten our critical edge computing infrastructure? | Zero-day and N-day vulnerabilities in edge platforms | What unpatched CVEs affecting our edge device vendors have been publicly disclosed in the last 90 days? | • CVE IDs for edge devices<br>• CVSS scores ≥ 7.0<br>• Proof-of-concept availability<br>• Vendor security advisories<br>• Exploit mentions in dark web | • Edge computing nodes<br>• IoT gateways<br>• CDN infrastructure | • Device firmware<br>• Configuration files<br>• API keys and tokens<br>• Customer data at edge |
| What insider threats exist within our supply chain? | Third-party vendor security incidents | Which of our critical vendors have experienced security breaches or insider incidents in the past 12 months? | • Breach notification documents<br>• News articles about vendors<br>• SEC filings mentioning incidents<br>• Social media disclosures<br>• Dark web data leak mentions | • Vendor access portals<br>• Supply chain management systems<br>• Third-party API connections | • Shared customer data<br>• Integrated system credentials<br>• Proprietary integration code |

### Using the Intelligence Requirements Model in Multi-Domain OSINT

The Intelligence Requirements Model applies across diverse operational environments. Here's how to use it effectively:

#### 1. **Define Your Scope**
Identify the domains relevant to your organization:
- **Enterprise IT/OT**: Cloud infrastructure, on-premises systems, industrial control systems
- **Telecommunications**: 5G/4G networks, backbone systems, subscriber management
- **Aviation/Transportation**: ATC systems, logistics platforms, passenger information systems
- **Defense**: Command and control systems, logistics networks, communications infrastructure
- **Critical Infrastructure**: Energy, water, healthcare, financial services systems
- **ICT/ICTS**: Information and communications technology supply chains
- **AI/ML Systems**: Training infrastructure, model repositories, inference endpoints
- **Secure Edge**: Edge computing, IoT gateways, distributed systems
- **Identity Systems**: Human and non-human identities (service accounts, API keys, certificates)

#### 2. **Map Your MES and HVAs**
Before defining requirements, inventory your:
- **Mission Essential Systems**: What systems are critical to operations?
- **High Value Assets**: What would adversaries most want to access or disrupt?

This mapping ensures intelligence collection focuses on protecting what matters most.

#### 3. **Build Requirements Top-Down**
Start with stakeholder CIRs and decompose systematically:
1. Engage leadership to understand their CIRs
2. Work with domain experts to derive CINs
3. Collaborate with analysts to define PIRs
4. Task collectors to identify specific EEIs

#### 4. **Align Collection to Requirements**
For each EEI, identify:
- **OSINT Sources**: Where can this information be found? (social media, public databases, forums, technical repositories, etc.)
- **Collection Methods**: How will we gather it? (manual searches, automated scrapers, API queries, etc.)
- **Collection Frequency**: How often do we need updates?
- **Indicators of Change**: What signals that this EEI needs re-collection?

#### 5. **Integrate Across Domains**
Modern threats don't respect domain boundaries. A threat actor might:
- Compromise IT systems to access OT networks
- Exploit telecom infrastructure to enable cyber espionage
- Target edge devices as entry points to cloud systems
- Use AI to enhance reconnaissance or social engineering

Your intelligence requirements should reflect these cross-domain attack paths.

#### 6. **Maintain and Iterate**
Intelligence requirements are living documents:
- Review PIRs monthly
- Update EEIs as the threat landscape changes
- Validate that collection activities still align with CIRs
- Remove or archive satisfied or obsolete requirements

### Example Multi-Domain Scenario

**Scenario**: A critical infrastructure organization operating energy distribution systems with cloud-managed SCADA, edge analytics, and AI-driven predictive maintenance.

**CIR**: "What are the active threats to our energy distribution operations?"

**CINs**:
1. Cyber threats to SCADA/ICS environments
2. Threats to cloud management infrastructure
3. Threats to edge analytics systems
4. Supply chain threats affecting AI/ML vendors

**Sample PIR (for CIN #1)**: "What threat groups have demonstrated capabilities to compromise Siemens SCADA systems in the energy sector within the past 6 months?"

**Sample EEIs**:
- Names and aliases of threat groups targeting energy sector
- IOCs (IP addresses, domains, file hashes) associated with Siemens SCADA attacks
- Public vulnerability disclosures for Siemens SCADA products
- Dark web discussions mentioning energy sector targeting
- Threat reports from DHS CISA, FBI, or industry ISACs

**Related MES**: SCADA master terminal units, historian databases, HMI workstations

**Related HVAs**: SCADA configuration files, authentication credentials, operational logs

### Action for This Repository / Review

> **NOTE TO @ltlfrappy21**: This Intelligence Requirements Model section represents a foundational framework for structured OSINT collection planning. Please review the following:
>
> 1. **Terminology**: Ensure CIR, CIN, PIR, EEI, MES, and HVA definitions align with your organizational or community standards.
> 2. **Examples**: Validate that the example mappings and multi-domain scenarios are relevant and accurate for the intended audience.
> 3. **Domains**: Confirm the listed operational domains (enterprise IT/OT, telecom, aviation, defense, etc.) cover the target use cases.
> 4. **Practical Guidance**: Review whether the "Using the Model" section provides sufficient actionable guidance for practitioners.
> 5. **Integration**: Assess how well this framework integrates with the other documents (QUICK-START-GUIDE, INVESTIGATION-WORKFLOWS).
>
> Your feedback will help ensure this framework serves the community effectively. Please comment on this PR with suggested revisions, additions, or clarifications.

---

## Collection Planning Process

### 1. Requirement Definition
- Identify stakeholder CIRs
- Decompose into CINs and PIRs
- Define specific EEIs
- Prioritize based on MES and HVAs

### 2. Source Identification
- Map EEIs to potential OSINT sources
- Evaluate source reliability and accessibility
- Consider legal and ethical constraints
- Document source access methods

### 3. Collection Strategy
- Develop collection workflows
- Assign collectors to requirements
- Establish collection schedules
- Define quality control measures

### 4. Execution and Management
- Execute collection activities
- Track progress against requirements
- Manage collected data and metadata
- Maintain operational security

### 5. Review and Adjustment
- Assess collection effectiveness
- Update requirements based on findings
- Refine collection methods
- Report to stakeholders

## OSINT Sources and Methods

### Source Categories
- **Social Media**: Twitter/X, Facebook, LinkedIn, Instagram, TikTok
- **Public Records**: Government databases, business registries, court records
- **Technical Sources**: GitHub, security advisories, vulnerability databases
- **News and Media**: News sites, blogs, press releases
- **Dark Web**: Forums, marketplaces (access with appropriate legal authority)
- **Geospatial**: Satellite imagery, mapping services
- **Infrastructure**: DNS records, WHOIS, certificate transparency logs

### Collection Methods
- **Manual Search**: Browser-based research and documentation
- **Automated Collection**: Scripts, APIs, web scraping tools
- **Monitoring**: Alert systems, RSS feeds, change detection
- **Network Analysis**: Tracking relationships and patterns
- **Temporal Analysis**: Trend identification over time

## Data Management

### Organization
- Structured storage of raw and processed data
- Metadata tagging for searchability
- Version control for evolving information
- Clear naming conventions

### Security
- Access controls based on data sensitivity
- Encryption for stored and transmitted data
- Regular backups
- Audit logging

### Retention
- Define retention periods by data type
- Comply with legal and regulatory requirements
- Secure disposal of outdated information

## Legal and Ethical Considerations

### Legal Compliance
- Respect terms of service for online platforms
- Comply with data protection regulations (GDPR, CCPA, etc.)
- Understand jurisdiction-specific laws
- Obtain appropriate legal authority for sensitive collection

### Ethical Guidelines
- Respect individual privacy
- Avoid deception or social engineering
- Consider potential harm from information disclosure
- Maintain professional standards

### Operational Security
- Protect collection methods and capabilities
- Use appropriate technical controls (VPNs, etc.)
- Avoid revealing collection activities to targets
- Protect analyst and collector safety

## Quality Control

### Verification
- Corroborate information across multiple sources
- Assess source reliability
- Document confidence levels
- Flag unverified information clearly

### Analysis Standards
- Apply structured analytical techniques
- Consider alternative hypotheses
- Identify gaps and assumptions
- Peer review when possible

### Reporting
- Tailor reports to audience
- Clearly separate facts from assessments
- Use appropriate classification/sensitivity markings
- Provide actionable recommendations

## Integration with Awesome OSINT Resources

This collection plan framework complements the extensive tool and resource listings in the main README. When executing collection activities:

1. **Reference the tool catalog**: Use tools listed in README.md for specific collection needs
2. **Match tools to EEIs**: Select appropriate tools based on the information you're seeking
3. **Follow workflows**: Refer to INVESTIGATION-WORKFLOWS.md for structured approaches
4. **Start quick**: Use QUICK-START-GUIDE.md for rapid orientation

The framework ensures that tool selection and usage remains aligned with defined intelligence requirements rather than ad-hoc exploration.

---

**Document Version**: 1.0  
**Last Updated**: 2025-12-30  
**Maintainer**: @ltlfrappy21
