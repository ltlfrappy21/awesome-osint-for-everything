# OSINT Collection Plan Framework

## Table of Contents

- [Overview](#overview)
- [The Intelligence Cycle](#the-intelligence-cycle)
- [Intelligence Requirements Framework](#intelligence-requirements-framework)
  - [Critical Intelligence Requirements (CIRs)](#critical-intelligence-requirements-cirs)
  - [Critical Intelligence Needs (CINs)](#critical-intelligence-needs-cins)
  - [Priority Intelligence Requirements (PIRs)](#priority-intelligence-requirements-pirs)
  - [Essential Elements of Information (EEIs)](#essential-elements-of-information-eeis)
- [Mission Essential Systems and High Value Assets](#mission-essential-systems-and-high-value-assets)
  - [Mission Essential Systems (MES)](#mission-essential-systems-mes)
  - [High Value Assets (HVAs)](#high-value-assets-hvas)
- [Mapping Intelligence Requirements to Collection](#mapping-intelligence-requirements-to-collection)
- [Templates and Examples by Sector](#templates-and-examples-by-sector)
- [Integration with Investigation Workflows](#integration-with-investigation-workflows)
- [Best Practices](#best-practices)

---

## Overview

An OSINT Collection Plan provides a structured approach to intelligence gathering using open-source information. This framework helps researchers, defenders, and investigators systematically identify what information is needed, where to find it, and how to collect it effectively.

**Purpose**: This document defines how to develop and execute OSINT collection plans using a requirements-driven approach that aligns with organizational intelligence needs and mission objectives.

**Audience**: Security researchers, threat intelligence analysts, red team operators, incident responders, risk assessors, and OSINT practitioners.

---

## The Intelligence Cycle

The Intelligence Cycle is the fundamental process by which intelligence is gathered, analyzed, and disseminated. OSINT collection planning operates within this cycle:

### 1. Planning and Direction
- **Define intelligence requirements** (CIRs, CINs, PIRs, EEIs)
- Identify stakeholders and consumers
- Establish collection priorities
- Allocate resources

### 2. Collection
- Execute collection plan using OSINT sources
- Gather information based on EEIs
- Document sources and methods
- Maintain collection logs

### 3. Processing and Exploitation
- Validate and verify collected information
- Organize and index data
- Translate or convert formats as needed
- Prepare for analysis

### 4. Analysis and Production
- Evaluate source reliability and information accuracy
- Identify patterns, trends, and anomalies
- Synthesize findings into intelligence products
- Answer PIRs and EEIs

### 5. Dissemination and Integration
- Deliver intelligence to stakeholders
- Present findings in appropriate formats
- Integrate into operational planning
- Archive for future reference

### 6. Feedback and Evaluation
- Assess intelligence effectiveness
- Refine requirements based on gaps
- Update collection priorities
- Improve processes and methods

**The collection plan links directly to Planning and Direction, informing what to collect and why.**

---

## Intelligence Requirements Framework

Intelligence requirements provide the structure for what information needs to be collected. They cascade from strategic to tactical levels, ensuring that collection efforts support decision-making.

### Critical Intelligence Requirements (CIRs)

**Definition**: Critical Intelligence Requirements are intelligence elements that directly support critical decisions by senior leadership. CIRs answer fundamental questions that affect organizational strategy, risk posture, or mission success.

**Characteristics**:
- Originate from senior leadership or key stakeholders
- Address strategic concerns with significant consequences
- Time-sensitive and actionable
- Limited in number (typically 3-7 per organization)
- Drive resource allocation and collection priorities

**Examples by Context**:

| Context | Example CIR |
|---------|-------------|
| **Enterprise IT Security** | What are the active threats targeting our critical business systems? |
| **Critical Infrastructure** | What threat actors have the capability and intent to disrupt our operations? |
| **Telecommunications** | What vulnerabilities exist in our 5G infrastructure that adversaries are exploiting? |
| **Aviation/Transportation** | What cyber threats pose risks to operational technology systems? |
| **Defense/Military** | What advanced persistent threats are targeting our classified networks? |
| **AI/ML Systems** | What adversaries are targeting AI model integrity or training data? |

### Critical Intelligence Needs (CINs)

**Definition**: Critical Intelligence Needs are the key questions or information categories that support CIRs. CINs break down strategic requirements into focused intelligence topics.

**Characteristics**:
- Derived directly from CIRs
- More specific than CIRs but still broad in scope
- Define major intelligence collection areas
- Typically 2-5 CINs support each CIR
- Bridge strategic intent to tactical collection

**Example CIR → CIN Mapping**:

**CIR**: What are the active threats targeting our critical business systems?

| CIN | Description |
|-----|-------------|
| **CIN 1** | Threat actor groups with demonstrated capabilities against our industry sector |
| **CIN 2** | Vulnerabilities in our technology stack being actively exploited in the wild |
| **CIN 3** | Attack patterns and TTPs used against similar organizations |
| **CIN 4** | Insider threat indicators and compromised credentials in threat actor spaces |

### Priority Intelligence Requirements (PIRs)

**Definition**: Priority Intelligence Requirements are specific questions that, when answered, address Critical Intelligence Needs. PIRs are the operational-level requirements that guide collection efforts.

**Characteristics**:
- Specific, answerable questions
- Time-bound (have explicit collection deadlines)
- Measurable (can determine when sufficiently answered)
- Directly support CINs
- Multiple PIRs typically support each CIN
- Assigned to specific collectors or teams

**Example CIN → PIR Mapping**:

**CIN**: Threat actor groups with demonstrated capabilities against our industry sector

| PIR | Collection Focus |
|-----|------------------|
| **PIR 1.1** | Which threat actors have published tooling or exploits targeting [specific technology]? |
| **PIR 1.2** | What threat groups have claimed attacks against organizations in our sector in the past 12 months? |
| **PIR 1.3** | Which threat actors are discussing our organization or sector in underground forums? |
| **PIR 1.4** | What are the known infrastructure patterns (domains, IPs, certificates) of threat actors targeting our sector? |

### Essential Elements of Information (EEIs)

**Definition**: Essential Elements of Information are the specific data points, indicators, or facts needed to answer PIRs. EEIs are the tactical-level requirements that directly guide OSINT collection activities.

**Characteristics**:
- Highly specific and granular
- Observable or discoverable through OSINT
- Mapped to specific collection sources
- Include indicators, observables, and factual data
- Multiple EEIs answer each PIR
- Include collection methods and sources

**Example PIR → EEI Mapping**:

**PIR**: Which threat actors have published tooling or exploits targeting [specific technology]?

| EEI | Data to Collect | OSINT Sources | Collection Method |
|-----|-----------------|---------------|-------------------|
| **EEI 1.1.1** | GitHub repositories containing exploit code for [CVE-YYYY-XXXX] | GitHub, GitLab, SourceForge | Code search, commit history analysis |
| **EEI 1.1.2** | Threat actor handles/aliases mentioned in exploit release announcements | Twitter/X, Mastodon, Pastebin | Social media monitoring, keyword searches |
| **EEI 1.1.3** | Proof-of-concept exploits shared in security researcher communities | YouTube, Medium, personal blogs | Content monitoring, RSS feeds |
| **EEI 1.1.4** | Tool download counts and fork activity indicating exploit adoption | GitHub API, npm, PyPI | Repository metrics, package statistics |

---

## Mission Essential Systems and High Value Assets

### Mission Essential Systems (MES)

**Definition**: Mission Essential Systems are the systems, networks, and technologies that are critical to an organization's core mission or operations. Disruption of MES directly impacts mission success.

**Characteristics**:
- Essential for organizational mission delivery
- Disruption causes significant operational impact
- Often targets of sophisticated threat actors
- Require priority protection and monitoring
- Inform intelligence collection priorities

**MES Categories by Sector**:

| Sector | Mission Essential Systems |
|--------|---------------------------|
| **Enterprise IT/OT** | ERP systems, manufacturing control systems, payment processing, customer databases |
| **Telecommunications** | Core network infrastructure, 5G base stations, billing systems, OSS/BSS platforms |
| **Aviation/Transportation** | Air traffic control systems, flight management systems, ticketing/reservation systems, logistics platforms |
| **Critical Infrastructure** | SCADA systems, industrial control systems (ICS), energy management systems, water treatment controls |
| **Defense** | Command and control systems, tactical communications, weapons systems, intelligence databases |
| **Financial Services** | Trading platforms, payment rails, fraud detection systems, regulatory reporting systems |
| **Healthcare** | Electronic health records, medical devices, laboratory information systems, pharmacy systems |
| **ICT/ICTS** | Network management systems, cloud orchestration, identity management, security operations platforms |

### High Value Assets (HVAs)

**Definition**: High Value Assets are specific resources—systems, data, people, or infrastructure—whose compromise would cause severe damage to the organization. HVAs may include MES but also encompass sensitive data, key personnel, and critical intellectual property.

**HVA Categories**:

1. **Systems and Technology**
   - Crown jewel databases
   - Proprietary algorithms or source code
   - Cryptographic key material
   - Authentication infrastructure
   - Backup and disaster recovery systems

2. **Data and Information**
   - Customer personal information (PII)
   - Financial records
   - Trade secrets and intellectual property
   - Strategic plans and M&A information
   - Security architecture documentation

3. **Infrastructure**
   - Internet-facing assets (web applications, APIs, email gateways)
   - Cloud infrastructure and containers
   - Network perimeter devices
   - Remote access solutions (VPN, RDP gateways)
   - Supply chain and third-party integrations

4. **Identities**
   - **Human Identities**: Privileged user accounts, executive accounts, administrator credentials, developers with code access
   - **Non-Human Identities (NHIDs)**: Service accounts, API keys, OAuth tokens, machine certificates, bot accounts, CI/CD pipeline credentials, cloud service principals

**Mapping MES and HVAs to Intelligence Requirements**:

MES and HVAs should directly inform CIRs, CINs, and PIRs. Protection of these assets drives intelligence requirements.

**Example Mapping**:

| MES/HVA | Related CIR | Related PIR |
|---------|-------------|-------------|
| **Cloud orchestration platform (MES)** | What threats target our cloud infrastructure? | What threat actors have demonstrated Kubernetes exploitation capabilities? |
| **Customer PII database (HVA)** | What are the active threats to our sensitive data? | What threat actors are selling access to databases in our industry? |
| **API service accounts (NHIDs/HVA)** | How are our non-human identities being targeted? | Where are leaked API keys from our organization appearing in public repositories? |
| **5G core network (MES)** | What vulnerabilities exist in our telecom infrastructure? | What exploits or attack tools target 5G core network functions? |

---

## Mapping Intelligence Requirements to Collection

The intelligence requirements framework creates a cascading structure from strategic to tactical:

```
CIR (Strategic Leadership Questions)
 ↓
CIN (Intelligence Topic Areas)
 ↓
PIR (Specific Intelligence Questions)
 ↓
EEI (Specific Data Points to Collect)
 ↓
Collection Activities (OSINT Sources and Methods)
```

**Flow Example**:

1. **CIR**: What are the active threats to our aviation operational technology?
2. **CIN**: Threat actors targeting aviation OT systems
3. **PIR**: Which threat groups have published exploits for aviation-specific industrial control systems?
4. **EEI**: List of GitHub repositories containing ICS exploits for [specific aviation system vendor]
5. **Collection**: Search GitHub using code search for vendor-specific exploit keywords, analyze commit history, identify contributors

This cascading structure ensures that every collection activity traces back to a strategic requirement, avoiding wasted effort on irrelevant information.

---

## Templates and Examples by Sector

The following templates provide reusable frameworks for developing intelligence requirements across different sectors and target types.

### Template 1: Enterprise IT/OT Security

**CIR**: What are the cyber threats to our enterprise IT and operational technology environments?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: Threat actors targeting our technology stack | PIR 1.1: Which threat actors have exploited vulnerabilities in [our major software vendors]? | - CVE exploitation timelines for our vendors<br>- Threat actor tooling specific to our stack<br>- Forum discussions of our vendor products |
| **CIN 2**: Vulnerabilities in our IT/OT convergence points | PIR 2.1: What published vulnerabilities affect our IT-OT gateway products? | - CVE databases for gateway vendors<br>- Security advisories for industrial protocols<br>- Exploit availability in public repositories |
| **CIN 3**: Attack patterns against similar organizations | PIR 3.1: What attack patterns have been used against organizations in our industry? | - Incident reports and case studies<br>- MITRE ATT&CK mappings for our sector<br>- Threat intelligence reports on industry attacks |
| **CIN 4**: Compromised credentials and insider threats | PIR 4.1: Are our employee credentials appearing in breach databases or darknet markets? | - Email addresses in breach databases<br>- Domain credentials in Telegram channels<br>- Employee accounts on underground forums |

**MES/HVA Focus**:
- MES: ERP system, manufacturing execution system, SCADA HMI
- HVAs: Product design databases, financial systems, privileged admin accounts, API service accounts (NHIDs)

### Template 2: Telecommunications and 5G Infrastructure

**CIR**: What cyber and physical threats target our telecommunications infrastructure?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: Vulnerabilities in 5G network functions | PIR 1.1: What vulnerabilities exist in 5G core network functions that are being actively researched? | - Security research papers on 5G vulnerabilities<br>- Conference presentations (Black Hat, DEF CON)<br>- Vendor security advisories for 5G equipment |
| **CIN 2**: Threat actors with telecom targeting capabilities | PIR 2.1: Which threat actors have historically targeted telecommunications providers? | - Attribution reports mentioning telecom targeting<br>- Malware families used against telecom operators<br>- Threat actor communication intercepts |
| **CIN 3**: Supply chain risks in network equipment | PIR 3.1: What supply chain compromises have affected telecom equipment vendors? | - Supply chain incident reports<br>- Vendor integrity investigations<br>- Third-party risk assessments |
| **CIN 4**: Signaling system vulnerabilities (SS7, Diameter) | PIR 4.1: What attacks leveraging SS7 or Diameter vulnerabilities have been documented? | - SS7 interception cases<br>- Diameter protocol attack tools<br>- Telecom security research publications |

**MES/HVA Focus**:
- MES: 5G core network, base stations, OSS/BSS, billing systems
- HVAs: Subscriber databases, authentication servers, lawful intercept systems, network management credentials (NHIDs)

### Template 3: Aviation and Transportation

**CIR**: What threats pose risks to our aviation operational technology and passenger safety systems?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: Cyber threats to flight operations systems | PIR 1.1: What vulnerabilities affect aircraft communication, navigation, and surveillance systems? | - CVEs for ACARS, ADS-B, and CPDLC systems<br>- Research on aircraft system hacking<br>- Proof-of-concept attacks on avionics |
| **CIN 2**: Ground operations and airport infrastructure threats | PIR 2.1: What threat actors target airport operational systems? | - Incidents affecting airport IT/OT systems<br>- Malware targeting airport infrastructure<br>- Threat actor interest in transportation sectors |
| **CIN 3**: Supply chain risks in aviation technology | PIR 3.1: What supply chain vulnerabilities exist in aircraft components and software? | - Vendor security advisories<br>- Component recalls due to security issues<br>- Software update integrity concerns |
| **CIN 4**: Drone and unmanned aerial system threats | PIR 4.1: What counter-UAS technologies and threats exist? | - UAS incident reports near airports<br>- Counter-drone system capabilities<br>- UAS jamming and spoofing techniques |

**MES/HVA Focus**:
- MES: Air traffic control, flight planning systems, baggage handling, fueling systems
- HVAs: Flight crew credentials, maintenance records, passenger manifests, navigation databases

### Template 4: Critical Infrastructure and Industrial Control Systems

**CIR**: What threat actors have the capability and intent to disrupt our critical infrastructure operations?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: ICS/SCADA vulnerabilities in our infrastructure | PIR 1.1: What vulnerabilities in our ICS vendors are being exploited in the wild? | - ICS-CERT advisories for our vendors<br>- Exploit code for our SCADA systems<br>- Vulnerability disclosures affecting our PLCs |
| **CIN 2**: State-sponsored threats to critical infrastructure | PIR 2.1: Which nation-state actors have targeted critical infrastructure in our country? | - Government attribution statements<br>- APT group profiles with infrastructure focus<br>- Intelligence agency reports on state threats |
| **CIN 3**: Physical and cyber convergence threats | PIR 3.1: What attacks have combined physical and cyber elements against infrastructure? | - Case studies of combined attacks<br>- Physical security bypass techniques<br>- Insider threat indicators |
| **CIN 4**: Operational technology protocol weaknesses | PIR 4.1: What attack tools exist for industrial protocols we use (Modbus, DNP3, etc.)? | - GitHub repositories with ICS attack tools<br>- Industrial protocol exploitation frameworks<br>- SCADA honeypot attack data |

**MES/HVA Focus**:
- MES: SCADA master servers, DCS controllers, safety instrumented systems, historian databases
- HVAs: Engineering workstations, firmware images, control system credentials (NHIDs), physical access control systems

### Template 5: Defense and Military Operations

**CIR**: What advanced persistent threats are targeting our classified and tactical networks?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: APT groups with capabilities against defense networks | PIR 1.1: Which APT groups have demonstrated capabilities against air-gapped or classified networks? | - APT group profiles and TTPs<br>- Malware families used in targeted attacks<br>- Zero-day exploits used by state actors |
| **CIN 2**: Threats to tactical communications and C4ISR | PIR 2.1: What vulnerabilities exist in tactical radio and communications systems? | - Security research on military communications<br>- SDR-based attack demonstrations<br>- Electronic warfare capabilities |
| **CIN 3**: Supply chain compromises in defense technology | PIR 3.1: What supply chain attacks have targeted defense contractors? | - Defense industrial base breach reports<br>- Compromised contractor systems<br>- Third-party software vulnerabilities |
| **CIN 4**: Threats to unmanned systems and autonomous platforms | PIR 4.1: What capabilities exist to jam, spoof, or hijack autonomous military systems? | - UAS interdiction technologies<br>- GPS spoofing and navigation attacks<br>- Autonomous system vulnerabilities |

**MES/HVA Focus**:
- MES: Command and control systems, intelligence databases, weapons systems, secure communications
- HVAs: Classified information, personnel security files, mission planning data, cryptographic keys (NHIDs)

### Template 6: AI/ML Systems and Secure Edge

**CIR**: What threat actors are targeting AI model integrity, training data, and edge computing infrastructure?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: Threats to AI/ML model integrity and training data | PIR 1.1: What adversarial AI techniques are being weaponized against production ML models? | - Research on adversarial machine learning<br>- Model poisoning attack demonstrations<br>- Data poisoning case studies |
| **CIN 2**: Threats to edge computing and IoT infrastructure | PIR 2.1: What vulnerabilities affect edge computing platforms and gateways? | - CVEs for edge computing platforms<br>- IoT device exploitation frameworks<br>- Edge gateway attack tools |
| **CIN 3**: AI-powered threats and automation | PIR 3.1: What threat actors are using AI for reconnaissance and attack automation? | - AI-powered attack tool development<br>- Automated reconnaissance frameworks<br>- LLM-based social engineering tools |
| **CIN 4**: Identity threats in AI systems (NHIDs) | PIR 4.1: How are API keys and service accounts for AI services being compromised? | - Leaked AI service API keys in GitHub<br>- Exposed ML model credentials<br>- Compromised cloud AI service accounts |

**MES/HVA Focus**:
- MES: ML training clusters, inference engines, edge AI processors, model registries
- HVAs: Training datasets, model weights, AI service credentials (NHIDs), edge device firmware

### Template 7: ICT/ICTS (Information and Communications Technology Supply Chain)

**CIR**: What supply chain risks exist in our information and communications technology ecosystem?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: Software supply chain compromises | PIR 1.1: What open-source dependencies in our stack have known vulnerabilities or have been compromised? | - Dependency vulnerability scans<br>- npm/PyPI/Maven malicious packages<br>- SolarWinds-style supply chain incidents |
| **CIN 2**: Hardware supply chain integrity | PIR 2.1: What evidence exists of hardware implants or backdoors in our vendor equipment? | - Hardware security research<br>- Chip-level backdoor discoveries<br>- Vendor integrity investigations |
| **CIN 3**: Third-party service provider risks | PIR 3.1: What security incidents have affected our SaaS and cloud service providers? | - Third-party breach notifications<br>- Cloud provider security advisories<br>- SaaS integration vulnerabilities |
| **CIN 4**: Certificate and PKI infrastructure threats | PIR 4.1: What certificate authority compromises or mis-issuances have occurred? | - CA incident reports<br>- Certificate transparency log anomalies<br>- TLS certificate abuse cases |

**MES/HVA Focus**:
- MES: Software development pipelines, package repositories, code signing infrastructure, certificate authorities
- HVAs: Source code repositories, CI/CD credentials (NHIDs), code signing keys, root CA certificates

### Template 8: Identity-Centric Intelligence Requirements

**CIR**: How are human and non-human identities being compromised, exploited, or targeted?

| CIN | PIR | EEI Examples |
|-----|-----|--------------|
| **CIN 1**: Human identity compromise | PIR 1.1: What employee credentials have been exposed in breaches or sold on darknet markets? | - Email addresses in breach databases<br>- Credentials in Telegram channels<br>- Employee accounts on underground forums |
| **CIN 2**: Non-human identity (NHID) exposure and abuse | PIR 2.1: What service accounts, API keys, and machine credentials are publicly exposed? | - GitHub secret scanning results<br>- Exposed .env files in public repositories<br>- API keys in Pastebin and paste sites |
| **CIN 3**: Privileged account targeting | PIR 3.1: What threat actors specifically target privileged and administrative accounts? | - Credential harvesting campaigns<br>- Phishing campaigns targeting admins<br>- Privilege escalation exploit usage |
| **CIN 4**: Identity infrastructure attacks | PIR 4.1: What attacks target Active Directory, Azure AD, and identity providers? | - Golden ticket and silver ticket attacks<br>- SAML and OAuth vulnerabilities<br>- Identity provider compromise incidents |

**MES/HVA Focus**:
- MES: Identity and access management systems, authentication servers, directory services
- HVAs: Domain administrator accounts, service principal credentials, OAuth tokens, certificate-based identities

---

## Integration with Investigation Workflows

Intelligence requirements should guide every phase of an OSINT investigation:

### 1. Investigation Scoping
- **Start with PIRs**: Define what questions the investigation must answer
- **Identify relevant EEIs**: Determine what specific data points are needed
- **Map to OSINT sources**: Identify which sources can provide the required information

### 2. Collection Execution
- **Prioritize by PIR**: Collect information that answers the highest-priority requirements first
- **Document EEI mapping**: Track which EEIs are being addressed by each collection activity
- **Maintain collection logs**: Record sources, timestamps, and methods used

### 3. Analysis and Reporting
- **Answer PIRs explicitly**: Structure reports around PIR answers
- **Identify gaps**: Document which PIRs remain unanswered and why
- **Provide confidence levels**: Assess the reliability of sources and accuracy of information

### 4. Feedback and Refinement
- **Update requirements**: Refine PIRs and EEIs based on findings
- **Generate new PIRs**: Identify follow-on questions that emerge from analysis
- **Improve collection methods**: Document lessons learned for future investigations

**Cross-References**:
- See [QUICK-START-GUIDE.md](QUICK-START-GUIDE.md) for rapid investigation techniques using PIRs
- See [INVESTIGATION-WORKFLOWS.md](INVESTIGATION-WORKFLOWS.md) for detailed workflow examples

---

## Best Practices

### Developing Effective Intelligence Requirements

1. **Start with the Decision**: What decision or action will this intelligence support?
2. **Be Specific**: Vague requirements produce vague intelligence
3. **Make it Answerable**: Ensure requirements can be satisfied with available sources
4. **Set Deadlines**: Time-bound requirements create urgency and focus
5. **Limit Number**: Too many requirements dilute effort (5-7 PIRs per investigation is ideal)
6. **Review Regularly**: Requirements should evolve as understanding improves

### Collection Planning Best Practices

1. **Requirements-Driven**: Never collect without a defined requirement
2. **Source Diversity**: Use multiple independent sources to validate information
3. **Document Everything**: Maintain detailed collection logs and source citations
4. **Legal and Ethical**: Ensure all collection activities comply with laws and policies
5. **OPSEC Aware**: Consider operational security when conducting collection
6. **Iterative Process**: Collection informs requirements, which inform collection

### Common Pitfalls to Avoid

- **Collection without Requirements**: Gathering information without clear purpose
- **Requirements Creep**: Continuously adding requirements without prioritization
- **Confirmation Bias**: Only collecting information that supports preconceptions
- **Single Source Reliance**: Failing to corroborate information across sources
- **Poor Documentation**: Inadequate source citation and collection tracking
- **Ignoring Gaps**: Failing to identify and address intelligence gaps

### Tools and Techniques

The main [README.md](README.md) provides an extensive catalog of OSINT tools organized by category. When developing collection plans:

1. **Map EEIs to Tool Categories**: Identify which tool categories support each EEI
2. **Build Collection Workflows**: Create repeatable processes using specific tools
3. **Automate Where Possible**: Use APIs and automation for routine collection tasks
4. **Maintain Toolset Currency**: Regularly review and update tools as sources evolve

---

## Review and Feedback

**⚠️ REVIEW REQUIRED**: This Intelligence Requirements framework (CIR/CIN/PIR/EEI/MES/HVA) is new content that requires review by @ltlfrappy21 before finalization.

**Feedback Areas**:
- Accuracy and completeness of definitions
- Appropriateness of examples for each sector
- Clarity of mapping templates
- Integration with existing repository content
- Additional sectors or use cases to include

---

## Additional Resources

- **Main Repository**: [README.md](README.md) - Comprehensive OSINT tool catalog
- **Quick Start**: [QUICK-START-GUIDE.md](QUICK-START-GUIDE.md) - Rapid investigation techniques
- **Workflows**: [INVESTIGATION-WORKFLOWS.md](INVESTIGATION-WORKFLOWS.md) - Step-by-step investigation processes

---

**Last Updated**: December 30, 2024  
**Version**: 1.0  
**Maintainer**: @ltlfrappy21
