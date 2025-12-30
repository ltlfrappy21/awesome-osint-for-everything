# OSINT Investigation Workflows

## Overview

This document provides structured workflows and decision trees for conducting OSINT investigations. Each workflow is designed to be systematic, repeatable, and aligned with intelligence requirements.

## Before You Start: Tie Workflows to PIRs and EEIs

**Every investigation workflow should be mapped to intelligence requirements.** Before beginning any workflow in this document, ensure you have:

### 1. Defined Your Priority Intelligence Requirement (PIR)
Your PIR is the specific question you're trying to answer. It provides purpose and boundaries for your investigation.

**Example PIRs:**
- "What infrastructure does adversary group X currently control?"
- "Has our organization's data appeared in recent breaches?"
- "What is the security posture of vendor Y?"
- "Where has username @target been active in the past 90 days?"

### 2. Identified Essential Elements of Information (EEIs)
EEIs are the specific data points you need to collect to answer your PIR. They guide which paths you take through the workflow.

**Example - For PIR "What infrastructure does adversary group X control?":**
- IP addresses currently attributed to the group
- Domain names under group control
- Hosting providers and registrars used
- SSL certificate fingerprints
- Network infrastructure patterns

**Example - For PIR "Has our organization's data appeared in recent breaches?":**
- Email addresses from our domain in breach databases
- Leaked credentials associated with our organization
- Mentions of our organization in dark web forums
- Data dumps containing our company name
- Timeline of when exposures occurred

### 3. Linked to Mission Essential Systems (MES) or High Value Assets (HVAs)
Understanding which critical systems or assets your investigation relates to helps prioritize findings and assess risk.

**Questions to ask:**
- Which MES could be affected by what I'm investigating?
- Which HVAs are at risk based on this intelligence?
- How does this investigation protect critical systems or assets?

### 4. Planned Your Collection Strategy
Based on your EEIs, identify:
- Which workflow sections are relevant
- What tools you'll need (from README.md)
- What sources you'll query
- How you'll document findings

**Mapping Example:**

| **PIR** | **EEI** | **Workflow Section** | **Tools Needed** | **Documentation** |
|---------|---------|---------------------|------------------|-------------------|
| What is the digital footprint of acme-corp.com? | DNS records, subdomains | Domain Investigation Workflow | DNS tools, certificate transparency | Spreadsheet tracking all subdomains |
| What is the digital footprint of acme-corp.com? | Technology stack | Domain Investigation Workflow | Wappalyzer, BuiltWith | Document with detected technologies |
| What is the digital footprint of acme-corp.com? | Employee profiles | People Investigation Workflow | LinkedIn, social media tools | Database of key employees |

### Benefits of This Approach

- **Focus**: You know exactly what you're looking for
- **Efficiency**: Skip irrelevant workflow branches
- **Completeness**: EEI checklist ensures nothing is missed
- **Quality**: PIR provides criteria for when investigation is complete
- **Traceability**: Clear line from findings back to requirements
- **Reporting**: Results directly answer stakeholder questions

**Best Practice**: Before starting any workflow below, write down:
1. Your PIR (one sentence)
2. Your 3-7 EEIs (bullet list)
3. Relevant MES/HVAs (if applicable)
4. Expected completion timeframe

This 2-minute planning step will save hours of unfocused investigation.

---

## Workflow 1: Domain/Organization Investigation

**Use when:** Investigating a company, organization, or specific domain

**Typical PIRs:**
- "What is the digital footprint of [organization]?"
- "What infrastructure does [domain] operate?"
- "What technologies does [organization] use?"

### Investigation Flow

```
START: Domain/Organization Investigation
    |
    v
[1] WHOIS Lookup
    |- Registration details
    |- Registrant information
    |- Name servers
    |- Registration dates
    |
    v
[2] DNS Enumeration
    |- A/AAAA records (IPs)
    |- MX records (email servers)
    |- TXT records (SPF, DMARC, verification)
    |- NS records (name servers)
    |- Subdomain enumeration
    |
    v
[3] Certificate Transparency
    |- Find SSL certificates
    |- Discover additional subdomains
    |- Identify certificate reuse
    |- Note certificate authorities
    |
    v
[4] Technology Profiling
    |- Web server identification
    |- CMS detection
    |- JavaScript frameworks
    |- Analytics platforms
    |- Third-party integrations
    |
    v
[5] Content Discovery
    |- Google dorking for files
    |- Directory brute-forcing (if authorized)
    |- Robots.txt examination
    |- Sitemap analysis
    |- Public file repositories
    |
    v
[6] Social Media Presence
    |- Official accounts
    |- Employee accounts
    |- Brand mentions
    |- Customer feedback
    |
    v
[7] Infrastructure Mapping
    |- ASN identification
    |- IP range enumeration
    |- Hosting provider
    |- CDN usage
    |- Cloud services
    |
    v
[8] Historical Analysis
    |- Wayback Machine snapshots
    |- DNS history
    |- WHOIS history
    |- Infrastructure changes
    |
    v
[9] Document and Analyze
    |- Compile findings
    |- Check EEI completeness
    |- Identify patterns
    |- Assess PIR satisfaction
    |
    v
END: Report Findings
```

### Decision Points

**At [2] DNS Enumeration:**
- **IF** subdomains discovered → Investigate each relevant subdomain (loop to [1])
- **IF** mail servers found → Document for email workflow if needed

**At [4] Technology Profiling:**
- **IF** vulnerable versions detected → Prioritize in findings
- **IF** uncommon technologies found → Research for known issues

**At [6] Social Media Presence:**
- **IF** significant employee presence → Consider people investigation workflow
- **IF** security incidents mentioned → Deep dive into mentions

---

## Workflow 2: People Investigation

**Use when:** Investigating individuals for legitimate purposes (hiring, fraud investigation, security research)

**Typical PIRs:**
- "What is the online presence of [person]?"
- "Are there security concerns related to [employee]?"
- "What information has [person] publicly disclosed?"

### Investigation Flow

```
START: People Investigation
    |
    v
[1] Initial Identification
    |- Full name variations
    |- Known usernames
    |- Email addresses
    |- Phone numbers
    |- Location information
    |
    v
[2] Search Engine Research
    |- Google search with quotes
    |- Bing search
    |- News mentions
    |- Blog posts/articles
    |- Forum posts
    |
    v
[3] Social Media Discovery
    |- Username searches across platforms
    |- LinkedIn profile
    |- Facebook presence
    |- Twitter/X activity
    |- Instagram, TikTok, etc.
    |
    v
[4] Professional Information
    |- LinkedIn detailed analysis
    |- Professional certifications
    |- Publications/patents
    |- Conference presentations
    |- GitHub/technical portfolios
    |
    v
[5] Contact Information
    |- Email addresses
    |- Phone numbers
    |- Physical addresses (if relevant and legal)
    |- Business contacts
    |
    v
[6] Data Breach Exposure
    |- HaveIBeenPwned checks
    |- Breach database searches
    |- Leaked credential checks
    |- Dark web mentions
    |
    v
[7] Digital Footprint Analysis
    |- Posting patterns
    |- Interest areas
    |- Connections/network
    |- Timeline of activity
    |- Behavioral patterns
    |
    v
[8] Cross-Reference and Verify
    |- Confirm identity across sources
    |- Validate information accuracy
    |- Check EEI completeness
    |- Note confidence levels
    |
    v
END: Compile Profile
```

### Ethical and Legal Considerations

**CRITICAL REMINDERS:**
- Only investigate for legitimate business or security purposes
- Respect privacy laws and regulations (GDPR, CCPA, etc.)
- Stay within legal boundaries
- Document justification for investigation
- Protect collected information appropriately

### Decision Points

**At [3] Social Media Discovery:**
- **IF** accounts found → Deep dive into public posts and connections
- **IF** accounts locked/private → Note and move on (do not attempt access)

**At [6] Data Breach Exposure:**
- **IF** credentials found → Assess security risk and report appropriately
- **IF** extensive exposure → Escalate to security team

---

## Workflow 3: Username Investigation

**Use when:** Starting with a username and expanding to find associated accounts and information

**Typical PIRs:**
- "Where does username [X] appear online?"
- "What information has [username] disclosed?"
- "What is the identity behind [username]?"

### Investigation Flow

```
START: Username Investigation
    |
    v
[1] Username Search Tools
    |- WhatsMyName
    |- Sherlock
    |- Namechk
    |- Username search engines
    |
    v
[2] Manual Platform Checks
    |- Twitter/X
    |- Reddit
    |- GitHub
    |- LinkedIn
    |- Instagram
    |- TikTok
    |- Discord
    |- Gaming platforms
    |
    v
[3] Search Engine Queries
    |- Google: "username"
    |- Google: username site:twitter.com
    |- Google: username site:github.com
    |- Bing and DuckDuckGo searches
    |
    v
[4] Profile Analysis
    |- Bio information
    |- Profile pictures (reverse search)
    |- Linked accounts
    |- Contact information
    |- Posted content
    |
    v
[5] Activity Timeline
    |- Account creation dates
    |- Post frequency
    |- Active hours/timezone
    |- Content evolution
    |
    v
[6] Connection Mapping
    |- Followers/following
    |- Mentioned users
    |- Collaboration partners
    |- Linked profiles
    |
    v
[7] Content Analysis
    |- Topics of interest
    |- Location mentions
    |- Personal information disclosure
    |- Behavioral patterns
    |
    v
[8] Cross-Reference Findings
    |- Link accounts to real identity (if possible)
    |- Verify information consistency
    |- Check EEIs
    |- Note contradictions
    |
    v
END: Compile Username Report
```

### Decision Points

**At [4] Profile Analysis:**
- **IF** profile picture found → Use reverse image search
- **IF** email in bio → Branch to email investigation workflow
- **IF** real name discovered → Branch to people investigation workflow

**At [6] Connection Mapping:**
- **IF** suspicious connections → Investigate related accounts
- **IF** burner/throwaway patterns → Note for analysis

---

## Workflow 4: Email Address Investigation

**Use when:** Starting with an email address

**Typical PIRs:**
- "Who owns this email address?"
- "Has this email been compromised?"
- "What accounts are associated with this email?"

### Investigation Flow

```
START: Email Investigation
    |
    v
[1] Email Validation
    |- Syntax check
    |- Domain validity
    |- MX record verification
    |- Deliverability test
    |
    v
[2] Breach Database Checks
    |- HaveIBeenPwned
    |- Dehashed
    |- LeakCheck
    |- Other breach databases
    |
    v
[3] Search Engine Research
    |- Google: "email@example.com"
    |- Find associated accounts
    |- Locate public mentions
    |- Discover linked profiles
    |
    v
[4] Social Media Association
    |- Check major platforms
    |- Look for account recovery options showing partial email
    |- Search for email in user profiles
    |
    v
[5] Username Extraction
    |- Extract username portion
    |- Run username investigation workflow
    |- Cross-reference findings
    |
    v
[6] Domain Investigation
    |- If corporate email → Domain workflow
    |- Check for email patterns in organization
    |- Identify other employees
    |
    v
[7] Associated Services
    |- Gravatar lookup
    |- GitHub association
    |- Pastebin mentions
    |- Forum registrations
    |
    v
[8] Data Enrichment
    |- Reverse email lookup tools
    |- People search engines
    |- Professional networks
    |- Contact databases
    |
    v
END: Email Report
```

### Decision Points

**At [2] Breach Database Checks:**
- **IF** breaches found → Document all breaches, dates, exposed data types
- **IF** recent breaches → Escalate priority

**At [6] Domain Investigation:**
- **IF** corporate domain → Run full domain investigation workflow
- **IF** personal domain → Note for ownership research

---

## Workflow 5: IP Address Investigation

**Use when:** Investigating IP addresses for threat intelligence or infrastructure mapping

**Typical PIRs:**
- "Who controls this IP address?"
- "Is this IP associated with malicious activity?"
- "What services are running on this IP?"

### Investigation Flow

```
START: IP Investigation
    |
    v
[1] Basic Identification
    |- WHOIS lookup
    |- Geolocation
    |- ASN identification
    |- ISP/hosting provider
    |
    v
[2] Reverse DNS
    |- PTR records
    |- Hostname identification
    |- Domain associations
    |
    v
[3] Threat Intelligence
    |- VirusTotal
    |- AbuseIPDB
    |- Shodan
    |- GreyNoise
    |- AlienVault OTX
    |
    v
[4] Service Enumeration
    |- Open ports (if authorized)
    |- Service banners
    |- SSL certificates
    |- Web services
    |
    v
[5] Historical Analysis
    |- Passive DNS records
    |- Historical WHOIS
    |- Previous domain associations
    |- Infrastructure changes
    |
    v
[6] Related Infrastructure
    |- Same ASN IPs
    |- Same certificate IPs
    |- Netblock enumeration
    |- Shared infrastructure patterns
    |
    v
[7] Reputation Assessment
    |- Blocklist checks
    |- Spam database checks
    |- Malware distribution history
    |- Attack source reports
    |
    v
[8] Reporting and Classification
    |- Compile findings
    |- Assess threat level
    |- Check EEIs
    |- Recommend actions
    |
    v
END: IP Intelligence Report
```

### Decision Points

**At [3] Threat Intelligence:**
- **IF** malicious indicators → Escalate immediately, expand investigation
- **IF** clean reputation → Continue standard workflow

**At [4] Service Enumeration:**
- **IF** unexpected services → Document and assess risk
- **IF** vulnerable services → Note for security team

---

## Workflow 6: Incident Response - Data Leak Investigation

**Use when:** Investigating potential or confirmed data leaks

**Typical PIRs:**
- "Has our organization's data been leaked?"
- "What data was exposed in [incident]?"
- "Where is our leaked data being shared?"

### Investigation Flow

```
START: Data Leak Investigation
    |
    v
[1] Incident Scoping
    |- What data types might be leaked?
    |- Timeframe of potential leak
    |- Potential leak sources
    |- Related MES and HVAs
    |
    v
[2] Breach Database Searches
    |- Search for organization domain
    |- Search for organization name
    |- Check employee emails
    |- Review breach timelines
    |
    v
[3] Dark Web Monitoring
    |- Forum searches
    |- Marketplace monitoring
    |- Paste sites (Pastebin, etc.)
    |- Data dump sites
    |
    v
[4] Social Media Monitoring
    |- Twitter/X breach announcements
    |- Security researcher disclosures
    |- Hacker community mentions
    |
    v
[5] Data Sample Acquisition
    |- Obtain samples (if legally possible)
    |- Verify authenticity
    |- Assess scope
    |- Document source
    |
    v
[6] Impact Assessment
    |- What data was exposed?
    |- How many records?
    |- Sensitivity classification
    |- Which HVAs affected?
    |
    v
[7] Source Investigation
    |- How was data obtained?
    |- When did breach occur?
    |- Who is responsible?
    |- What vulnerabilities exploited?
    |
    v
[8] Containment and Reporting
    |- Alert security team
    |- Notify affected parties (if required)
    |- Document for compliance
    |- Plan remediation
    |
    v
END: Incident Report
```

### Critical Actions

**IMMEDIATELY:**
- Alert incident response team
- Document all findings with timestamps
- Preserve evidence
- Do not download large amounts of leaked data (legal concerns)

---

## Workflow 7: Threat Actor Investigation

**Use when:** Researching threat actors, adversary groups, or suspicious entities

**Typical PIRs:**
- "What infrastructure does [threat actor] control?"
- "What are [group]'s TTPs?"
- "Is [threat actor] currently active?"

### Investigation Flow

```
START: Threat Actor Investigation
    |
    v
[1] Intelligence Gathering
    |- Known aliases and names
    |- Historical activity
    |- Attributed campaigns
    |- Industry reports
    |
    v
[2] Infrastructure Mapping
    |- Known IP addresses
    |- Domain names
    |- Hosting providers
    |- Certificate patterns
    |- Network infrastructure
    |
    v
[3] TTP Analysis
    |- Attack vectors
    |- Exploitation techniques
    |- Malware families used
    |- C2 communication methods
    |- Persistence mechanisms
    |
    v
[4] Attribution Indicators
    |- Language artifacts
    |- Timezone patterns
    |- Code similarities
    |- Operational patterns
    |- Geopolitical motivations
    |
    v
[5] Current Activity Monitoring
    |- Active infrastructure
    |- Recent campaigns
    |- Latest tool development
    |- Forum activity
    |- Social media presence
    |
    v
[6] Target Analysis
    |- Targeted sectors
    |- Geographic focus
    |- Organization types
    |- Victimology patterns
    |
    v
[7] Capability Assessment
    |- Technical sophistication
    |- Resources available
    |- Likely nation-state backing
    |- Innovation level
    |
    v
[8] Intelligence Product Creation
    |- Compile threat profile
    |- Map to MES/HVAs
    |- Create IOC list
    |- Recommend defenses
    |
    v
END: Threat Actor Profile
```

### Sources for Threat Intelligence

- Public threat reports (vendor blogs, research papers)
- Government advisories (CISA, FBI, NSA)
- Threat intelligence platforms
- Security community forums
- Dark web monitoring
- Malware repositories

---

## Workflow 8: Technology/Vulnerability Investigation

**Use when:** Researching specific technologies, CVEs, or vulnerabilities

**Typical PIRs:**
- "What vulnerabilities affect [technology]?"
- "Is CVE-XXXX-XXXXX being actively exploited?"
- "What products are affected by [vulnerability]?"

### Investigation Flow

```
START: Technology/Vulnerability Investigation
    |
    v
[1] Vulnerability Identification
    |- CVE number
    |- Affected products/versions
    |- Severity score (CVSS)
    |- Discovery date
    |
    v
[2] Vendor Information
    |- Official advisories
    |- Patch availability
    |- Workarounds
    |- EOL status
    |
    v
[3] Exploitation Status
    |- Proof-of-concept availability
    |- Exploit code in wild
    |- Metasploit modules
    |- Active exploitation reports
    |
    v
[4] Affected Asset Identification
    |- Which MES use this technology?
    |- Internal asset inventory check
    |- Version identification
    |- Exposure assessment
    |
    v
[5] Threat Actor Interest
    |- Dark web mentions
    |- Hacker forum discussions
    |- Observed in campaigns
    |- Trending on social media
    |
    v
[6] Impact Assessment
    |- Potential damage
    |- Attack complexity
    |- Required privileges
    |- User interaction needed
    |
    v
[7] Mitigation Research
    |- Available patches
    |- Configuration changes
    |- Compensating controls
    |- Detection signatures
    |
    v
[8] Reporting and Tracking
    |- Document findings
    |- Prioritize remediation
    |- Track patching status
    |- Monitor for exploitation
    |
    v
END: Vulnerability Report
```

---

## General Best Practices Across All Workflows

### Documentation Standards
- **Timestamp all findings**: Note when information was collected
- **Source attribution**: Record where each piece of information came from
- **Chain of custody**: Maintain evidence integrity
- **Confidence levels**: Rate reliability of information (High/Medium/Low)
- **EEI tracking**: Maintain checklist of EEIs and mark as complete

### Quality Control
- **Verify information**: Use multiple sources when possible
- **Question assumptions**: Don't take information at face value
- **Consider deception**: Be aware of false flags and disinformation
- **Peer review**: Have findings reviewed when possible

### Operational Security
- **Use VPNs**: Protect your investigation activities
- **Separate browsers**: Don't mix personal and investigation activities
- **Clean metadata**: Remove metadata from screenshots/documents
- **Secure storage**: Protect collected intelligence appropriately

### Reporting
- **Match format to audience**: Technical vs. executive summaries
- **Answer the PIR**: Ensure findings directly address the original question
- **Include gaps**: Identify what you couldn't find
- **Provide recommendations**: Actionable next steps

### Integration with Collection Planning

These workflows implement the structured approach defined in:
- **[OSINT-COLLECTION-PLAN.md](OSINT-COLLECTION-PLAN.md)** - Maps EEIs to collection activities
- **[QUICK-START-GUIDE.md](QUICK-START-GUIDE.md)** - Provides rapid entry points to workflows
- **[README.md](README.md)** - Tool catalog for workflow execution

---

## Workflow Selection Matrix

| **Starting Point** | **Use Workflow** | **Typical PIR** |
|-------------------|------------------|-----------------|
| Domain name | Domain/Organization Investigation | "What is org's infrastructure?" |
| Person name | People Investigation | "What is person's online presence?" |
| Username | Username Investigation | "Where does username appear?" |
| Email address | Email Investigation | "Who owns this email?" |
| IP address | IP Investigation | "Who controls this IP?" |
| Suspected leak | Data Leak Investigation | "Has our data leaked?" |
| Threat actor name | Threat Actor Investigation | "What are actor's capabilities?" |
| CVE or technology | Technology/Vulnerability Investigation | "Are we affected by this CVE?" |

---

**Document Version**: 1.0  
**Last Updated**: 2025-12-30  
**Maintainer**: @ltlfrappy21

## Contributing

Have a workflow to add or improve? Contributions welcome! Please ensure workflows:
- Are mapped to PIRs and EEIs
- Include clear decision points
- Reference tools from README.md
- Follow documentation standards
