# OSINT Investigation Workflows

# <<<<<<< copilot/build-collection-plan-osint
Visual workflows and decision trees for different types of OSINT investigations.

## Table of Contents
- [General Investigation Workflow](#general-investigation-workflow)
- [Person Investigation Workflow](#person-investigation-workflow)
- [Domain Investigation Workflow](#domain-investigation-workflow)
- [Company Investigation Workflow](#company-investigation-workflow)
- [Email Investigation Workflow](#email-investigation-workflow)
- [Username Investigation Workflow](#username-investigation-workflow)
- [Threat Intelligence Workflow](#threat-intelligence-workflow)
- [Decision Trees](#decision-trees)

---

## General Investigation Workflow

```
┌─────────────────────────────────────────────────────────────┐
│                    START INVESTIGATION                       │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              PHASE 1: PLANNING (10% time)                   │
├─────────────────────────────────────────────────────────────┤
│  1. Define intelligence requirements                        │
│  2. Identify information sources                            │
│  3. Select appropriate tools                                │
│  4. Establish legal/ethical boundaries                      │
│  5. Set timeline and milestones                             │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│             PHASE 2: COLLECTION (40% time)                  │
├─────────────────────────────────────────────────────────────┤
│  1. Execute search strategies                               │
│  2. Gather data from identified sources                     │
│  3. Document findings continuously                          │
│  4. Archive evidence properly                               │
│  5. Pivot based on discoveries                              │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│             PHASE 3: PROCESSING (20% time)                  │
├─────────────────────────────────────────────────────────────┤
│  1. Organize collected information                          │
│  2. Validate data accuracy                                  │
│  3. Cross-reference sources                                 │
│  4. Identify gaps and conflicts                             │
│  5. Clean and structure data                                │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              PHASE 4: ANALYSIS (20% time)                   │
├─────────────────────────────────────────────────────────────┤
│  1. Link analysis (relationships)                           │
│  2. Timeline analysis (events)                              │
│  3. Pattern recognition                                     │
│  4. Draw conclusions                                        │
│  5. Identify intelligence gaps                              │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│            PHASE 5: DISSEMINATION (10% time)                │
├─────────────────────────────────────────────────────────────┤
│  1. Create intelligence products                            │
│  2. Visualize findings                                      │
│  3. Write reports                                           │
│  4. Present to stakeholders                                 │
│  5. Archive case files                                      │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
                 ┌───────────────┐
                 │   CASE CLOSED  │
                 └───────────────┘
```

---

## Person Investigation Workflow

```
                    TARGET: Person/Identity
                             │
                             ▼
        ┌────────────────────────────────────────┐
        │      START: What do we know?           │
        │  • Name (variations)                   │
        │  • Age/DOB (approximate)               │
        │  • Location (past/present)             │
        │  • Known email/phone/username          │
        └────────────┬───────────────────────────┘
                     │
        ┌────────────┴────────────┐
        │                         │
        ▼                         ▼
   ┌─────────┐            ┌──────────────┐
   │ GOOGLE  │            │ SOCIAL MEDIA │
   │ SEARCH  │            │    SEARCH    │
   └────┬────┘            └──────┬───────┘
        │                        │
        │  Find:                 │  Check:
        │  • News articles       │  • Facebook
        │  • Public records      │  • LinkedIn
        │  • Mentions            │  • Twitter/X
        │  • Images              │  • Instagram
        │                        │  • TikTok
        └────────┬───────────────┘
                 │
                 ▼
        ┌────────────────┐
        │ USERNAME SEARCH │
        │ • WhatsMyName   │
        │ • Sherlock      │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │  EMAIL/PHONE     │
        │  • HIBP          │
        │  • Dehashed      │
        │  • TrueCaller    │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │  PUBLIC RECORDS  │
        │  • Court records │
        │  • Property      │
        │  • Business      │
        │  • Licenses      │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │  DEEP WEB CHECK  │
        │  • Breaches      │
        │  • Pastes        │
        │  • Forums        │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────────┐
        │  COMPILE & ANALYZE   │
        │  • Build timeline    │
        │  • Map relationships │
        │  • Verify info       │
        └──────────────────────┘
```

**Key Decision Points:**
- Found email? → Run through breach databases
- Found username? → Cross-platform search
- Found location? → Check local records
- Found employer? → LinkedIn + company records
- Found social media? → Archive and analyze posts

---

## Domain Investigation Workflow

```
                TARGET: example.com
                        │
                        ▼
        ┌───────────────────────────┐
        │   REGISTRATION INFO       │
        │   • WHOIS lookup          │
        │   • Historical WHOIS      │
        │   • Registrar details     │
        └───────────┬───────────────┘
                    │
        ┌───────────┴────────────┐
        │                        │
        ▼                        ▼
   ┌──────────┐         ┌──────────────┐
   │   DNS    │         │ SUBDOMAINS   │
   │  RECORDS │         │  • crt.sh    │
   │          │         │  • DNSDumpster│
   └────┬─────┘         └──────┬───────┘
        │                      │
        └──────────┬───────────┘
                   │
                   ▼
        ┌──────────────────┐
        │   IP ANALYSIS    │
        │   • Geolocation  │
        │   • ASN info     │
        │   • Hosting      │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │  SSL/TLS CERTS   │
        │  • Certificate   │
        │  • Validity      │
        │  • History       │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │  TECHNOLOGY      │
        │  • Wappalyzer    │
        │  • BuiltWith     │
        │  • Server info   │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │  CONTENT         │
        │  • Current site  │
        │  • Wayback       │
        │  • Robots.txt    │
        │  • Sitemap       │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │  SECURITY        │
        │  • VirusTotal    │
        │  • URLScan       │
        │  • Shodan        │
        │  • Blacklists    │
        └──────────────────┘
```

**Key Actions:**
- Active domain? → Full infrastructure analysis
- Expired domain? → Historical analysis only
- Found subdomains? → Investigate each separately
- Security issues? → Document and report
- Related domains? → Expand investigation

---

## Company Investigation Workflow

```
              TARGET: Company Name
                      │
                      ▼
        ┌─────────────────────────┐
        │   BASIC INFORMATION     │
        │   • Official website    │
        │   • Google search       │
        │   • Social media        │
        └──────────┬──────────────┘
                   │
        ┌──────────┴─────────┐
        │                    │
        ▼                    ▼
   ┌──────────┐       ┌──────────────┐
   │ BUSINESS │       │   PEOPLE     │
   │ RECORDS  │       │   • Officers │
   │          │       │   • Employees│
   └────┬─────┘       └──────┬───────┘
        │                    │
        │  • Registration    │
        │  • Incorporation   │
        │  • Tax ID          │
        │  • Licenses        │
        │                    │
        └─────────┬──────────┘
                  │
                  ▼
        ┌──────────────────┐
        │  DIGITAL ASSETS  │
        │  • Domains       │
        │  • Email addrs   │
        │  • IP ranges     │
        │  • Social media  │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │   FINANCIAL      │
        │  • Revenue       │
        │  • Funding       │
        │  • Public filings│
        │  • Credit rating │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │   RELATIONSHIPS  │
        │  • Parent co.    │
        │  • Subsidiaries  │
        │  • Partners      │
        │  • Competitors   │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │   REPUTATION     │
        │  • Reviews       │
        │  • Complaints    │
        │  • Legal issues  │
        │  • News          │
        └──────────────────┘
```

**Investigation Paths:**
- Public company? → SEC filings, investor relations
- Private company? → Business registrations, credit reports
- International? → Check country-specific databases
- Suspicious activity? → Legal/court records
- Technology company? → GitHub, patents, products

---

## Email Investigation Workflow

```
              TARGET: email@example.com
                          │
                          ▼
        ┌─────────────────────────────┐
        │    VALIDATION CHECK          │
        │    • Format valid?           │
        │    • Domain active?          │
        │    • Deliverable?            │
        └──────────┬──────────────────┘
                   │
                   ▼
        ┌─────────────────────────────┐
        │    BREACH DATABASES          │
        │    • Have I Been Pwned       │
        │    • Dehashed                │
        │    • LeakCheck               │
        │    • Intelligence X          │
        └──────────┬──────────────────┘
                   │
          ┌────────┴────────┐
          ▼                 ▼
    ┌──────────┐      ┌──────────┐
    │ SOCIAL   │      │ SEARCH   │
    │ MEDIA    │      │ ENGINES  │
    │ PROFILES │      │          │
    └────┬─────┘      └────┬─────┘
         │                 │
         └────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │  DOMAIN ANALYSIS │
        │  • Company email?│
        │  • Personal?     │
        │  • Disposable?   │
        └─────────┬────────┘
                  │
                  ▼
        ┌──────────────────┐
        │  RELATED INFO    │
        │  • Other emails  │
        │  • Usernames     │
        │  • Phone numbers │
        │  • Real name     │
        └──────────────────┘
```

**Email Type Actions:**
- Corporate email → Investigate company + person
- Personal email (Gmail, Yahoo) → Focus on person
- Disposable/temp email → Limited intel, focus on usage
- Compromised email → Check breach details for other info

---

## Username Investigation Workflow

```
                TARGET: username123
                          │
                          ▼
        ┌──────────────────────────────┐
        │  CROSS-PLATFORM SEARCH       │
        │  • WhatsMyName               │
        │  • Sherlock                  │
        │  • Manual platform checks    │
        └──────────┬───────────────────┘
                   │
                   ▼
        ┌──────────────────────────────┐
        │  FOUND PROFILES?             │
        └───┬──────────────────┬───────┘
            │ YES              │ NO
            ▼                  ▼
    ┌───────────────┐   ┌────────────┐
    │ ANALYZE EACH  │   │  TRY       │
    │ PROFILE:      │   │  VARIATIONS│
    │ • Content     │   │  • _       │
    │ • Dates       │   │  • -       │
    │ • Location    │   │  • numbers │
    │ • Links       │   └────────────┘
    │ • Metadata    │
    └───────┬───────┘
            │
            ▼
    ┌──────────────────┐
    │ IDENTIFY PERSON  │
    │ • Real name      │
    │ • Email          │
    │ • Location       │
    │ • Other usernames│
    └─────────┬────────┘
              │
              ▼
    ┌──────────────────┐
    │  BUILD PROFILE   │
    │  • Timeline      │
    │  • Interests     │
    │  • Network       │
    │  • Activity      │
    └──────────────────┘
```

**Username Analysis Tips:**
- Unique username → Easier to track
- Common username → More verification needed
- Username variations → Check all variants
- Inactive profiles → Still valuable for historical data

---

## Threat Intelligence Workflow

```
            TARGET: Threat Actor/IOC
                        │
                        ▼
        ┌───────────────────────────┐
        │   IDENTIFY IOC TYPE       │
        │   • IP address            │
        │   • Domain                │
        │   • File hash             │
        │   • Email                 │
        │   • Username              │
        └──────────┬────────────────┘
                   │
                   ▼
        ┌──────────────────────────┐
        │  THREAT INTEL PLATFORMS  │
        │  • VirusTotal            │
        │  • AlienVault OTX        │
        │  • ThreatMiner           │
        │  • Shodan                │
        └──────────┬───────────────┘
                   │
                   ▼
        ┌──────────────────────────┐
        │  MALWARE ANALYSIS        │
        │  • Hybrid Analysis       │
        │  • ANY.RUN               │
        │  • Joe Sandbox           │
        └──────────┬───────────────┘
                   │
                   ▼
        ┌──────────────────────────┐
        │  INFRASTRUCTURE          │
        │  • C2 servers            │
        │  • Related domains       │
        │  • IP ranges             │
        │  • Hosting providers     │
        └──────────┬───────────────┘
                   │
                   ▼
        ┌──────────────────────────┐
        │  ATTRIBUTION             │
        │  • Known campaigns       │
        │  • APT groups            │
        │  • TTPs                  │
        │  • Historical activity   │
        └──────────┬───────────────┘
                   │
                   ▼
        ┌──────────────────────────┐
        │  REPORTING               │
        │  • IOC list              │
        │  • YARA rules            │
        │  • Mitigation steps      │
        │  • Threat brief          │
        └──────────────────────────┘
```

**IOC Investigation Paths:**
- File hash → Malware analysis + OSINT
- IP address → Infrastructure mapping + geolocation
- Domain → Registration + historical + relationships
- Email → Attribution + campaigns + related IOCs

---

## Decision Trees

### Decision Tree: Where to Start?

```
                    What type of target?
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
        ▼                   ▼                   ▼
    [PERSON]            [ENTITY]          [TECHNICAL]
        │                   │                   │
        │                   ├─ Company          ├─ Domain/Website
        │                   ├─ Organization     ├─ IP Address
        │                   └─ Group            ├─ Email
        │                                       ├─ Phone
        ▼                                       └─ Username
What info do you have?                              │
    │                                               │
    ├─ Name only → Google + Social Media            │
    ├─ Email → Breach DB + Email Tools              │
    ├─ Username → WhatsMyName + Platforms           │
    ├─ Phone → Reverse lookup + Carrier             │
    ├─ Photo → Reverse image + Social               │
    └─ Location → Maps + Public Records             │
                                                    │
                                                    ▼
                                          What's the goal?
                                                    │
                                    ┌───────────────┼───────────────┐
                                    │               │               │
                                    ▼               ▼               ▼
                              [IDENTIFY]    [INVESTIGATE]    [MONITOR]
                                Owner         Security        Changes
                                Contact       Reputation       Activity
                                History       Trust            Threats
```

### Decision Tree: Investigation Scope

```
                How much time do you have?
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
        ▼                 ▼                 ▼
    [< 30 MIN]        [1-4 HOURS]      [DAYS/WEEKS]
        │                 │                 │
        │                 │                 │
Quick recon:        Deep dive:        Comprehensive:
• Google            • All quick       • Everything
• Main social       • Public records  • Deep web
• Basic checks      • Historical data • Relationships
│                   • Cross-reference • Timeline
│                   │                 • Analysis
▼                   ▼                 ▼
Minimal intel   Good overview    Complete picture
```

### Decision Tree: Legal Concerns

```
                Is this action legal?
                        │
            ┌───────────┴───────────┐
            │                       │
            ▼                       ▼
        [YES/UNSURE]            [NO/ILLEGAL]
            │                       │
            │                       ▼
            │                  DON'T DO IT!
            │                   STOP HERE
            ▼
    Does it violate ToS?
            │
    ┌───────┴───────┐
    │               │
    ▼               ▼
  [YES]           [NO]
    │               │
    │               ▼
    │         Do you have
    │         authorization?
    │               │
    │       ┌───────┴───────┐
    │       │               │
    │       ▼               ▼
    │    [YES]           [NO]
    │       │               │
    │       │               ▼
    │       │         Get authorization
    │       │         or use alternative
    │       ▼               method
    │   PROCEED
    │   (document
    │   everything)
    │
    ▼
Consider alternative
that doesn't violate ToS
```

---

## Quick Reference: Investigation Phases

### Phase 1: Planning
**Time:** 10% of investigation  
**Focus:** Strategy and preparation  
**Output:** Collection plan, tool list, boundaries

### Phase 2: Collection
**Time:** 40% of investigation  
**Focus:** Gathering information  
**Output:** Raw data, screenshots, archives

### Phase 3: Processing
**Time:** 20% of investigation  
**Focus:** Organization and validation  
**Output:** Structured data, verified facts

### Phase 4: Analysis
**Time:** 20% of investigation  
**Focus:** Finding meaning and connections  
**Output:** Insights, patterns, conclusions

### Phase 5: Dissemination
**Time:** 10% of investigation  
**Focus:** Reporting and presentation  
**Output:** Reports, visualizations, briefings

---

## Common Investigation Patterns

### Pattern: Pivot Investigation
```
Start → Find username → Search username → Find email →
Search email → Find name → Search name → Find location →
Search location → Find associates → Expand investigation
```

### Pattern: Verification Loop
```
Find information → Cross-reference → 
If matches: Accept → If conflicts: Investigate further →
Find more sources → Re-verify
```

### Pattern: Breadth-First vs Depth-First

**Breadth-First:** Good for initial discovery
```
Person → All social media (quick check) → 
All public records (quick check) → All usernames (quick check)
```

**Depth-First:** Good for thorough investigation
```
Person → Facebook (complete analysis) → 
Extract all info → Follow all leads from Facebook →
Then move to next platform
```

---

## Tool Selection by Investigation Phase

### Planning Phase Tools
- Note-taking: Markdown editors, OneNote
- Mind mapping: MindMup, XMind
- Project management: Trello, Notion

### Collection Phase Tools
- Browsers: Chrome/Firefox with extensions
- Archiving: Wayback Machine, Archive.is
- Screenshots: Built-in or Greenshot
- Search: Google, specialized search engines

### Processing Phase Tools
- Spreadsheets: Excel, Google Sheets
- Database: SQLite, Airtable
- Text processing: Python, text editors

### Analysis Phase Tools
- Link analysis: Maltego, Lampyre
- Timeline: TimelineJS, Excel
- Visualization: Gephi, Graphviz

### Dissemination Phase Tools
- Reporting: Word, Google Docs, LaTeX
- Presentation: PowerPoint, Google Slides
- Visualization: Charts, graphs, maps

---

**For complete tool listings and detailed methodologies, refer to:**
- [Main Repository](README.md)
- [OSINT Collection Plan](OSINT-COLLECTION-PLAN.md)
- [Quick Start Guide](QUICK-START-GUIDE.md)

**Last Updated:** December 2025
# =======
## Table of Contents

- [Introduction](#introduction)
- [Investigation Workflow Fundamentals](#investigation-workflow-fundamentals)
- [Workflow 1: Domain and IP Address Investigation](#workflow-1-domain-and-ip-address-investigation)
- [Workflow 2: Identity and Credential Investigation](#workflow-2-identity-and-credential-investigation)
- [Workflow 3: Threat Actor Profiling](#workflow-3-threat-actor-profiling)
- [Workflow 4: Malware and IOC Analysis](#workflow-4-malware-and-ioc-analysis)
- [Workflow 5: Social Media Intelligence (SOCMINT)](#workflow-5-social-media-intelligence-socmint)
- [Workflow 6: Supply Chain and Third-Party Risk Assessment](#workflow-6-supply-chain-and-third-party-risk-assessment)
- [Workflow 7: Critical Infrastructure Threat Assessment](#workflow-7-critical-infrastructure-threat-assessment)
- [Workflow 8: Identity Surface Investigation (Human and Non-Human)](#workflow-8-identity-surface-investigation-human-and-non-human)
- [Using Intelligence Requirements in Workflows](#using-intelligence-requirements-in-workflows)
- [Workflow Documentation Templates](#workflow-documentation-templates)
- [Advanced Techniques](#advanced-techniques)

---

## Introduction

This document provides step-by-step workflows for common OSINT investigation scenarios. Each workflow integrates intelligence requirements (PIRs and EEIs) to ensure focused, efficient collection that answers specific questions.

**How to Use These Workflows**:
1. Select the workflow that matches your investigation type
2. Review the PIR examples and adapt them to your specific case
3. Follow the collection steps systematically
4. Document findings using the provided templates
5. Conduct analysis and reporting as outlined

**Prerequisite Reading**:
- [OSINT-COLLECTION-PLAN.md](OSINT-COLLECTION-PLAN.md) - Understanding intelligence requirements
- [QUICK-START-GUIDE.md](QUICK-START-GUIDE.md) - Rapid investigation basics

---

## Investigation Workflow Fundamentals

### Core Workflow Pattern

Every OSINT investigation follows this pattern:

```
REQUIREMENTS → COLLECTION → PROCESSING → ANALYSIS → REPORTING → FEEDBACK
```

**Requirements Phase**:
- Define PIRs (Priority Intelligence Requirements)
- Break down into EEIs (Essential Elements of Information)
- Identify collection sources and methods

**Collection Phase**:
- Execute searches and queries systematically
- Gather information from identified sources
- Document sources, methods, and timestamps

**Processing Phase**:
- Organize and structure collected data
- Validate information quality and accuracy
- Identify relationships and patterns

**Analysis Phase**:
- Answer PIRs using collected information
- Assess confidence levels
- Identify intelligence gaps

**Reporting Phase**:
- Document findings and evidence
- Present conclusions to stakeholders
- Archive investigation materials

**Feedback Phase**:
- Review effectiveness of collection
- Refine requirements based on findings
- Generate follow-on PIRs

### Intelligence Requirements Integration

Each workflow in this document includes:
- **Sample PIRs**: Example Priority Intelligence Requirements for this investigation type
- **EEI Mapping**: How EEIs map to specific collection steps
- **Source Selection**: Which OSINT sources address which EEIs
- **Gap Identification**: Common intelligence gaps and how to address them

---

## Workflow 1: Domain and IP Address Investigation

### Use Cases
- Investigating suspicious domains or IPs
- Attribution of infrastructure to threat actors
- Identifying related infrastructure (domain clusters)
- Assessing reputation and risk of external entities

### Sample PIRs for Domain Investigation

1. **PIR 1**: Who owns this domain and what other domains do they control?
2. **PIR 2**: What is the technical infrastructure supporting this domain (IP, hosting, nameservers)?
3. **PIR 3**: What is the historical activity and reputation of this domain?
4. **PIR 4**: What content and services are hosted on this domain?
5. **PIR 5**: Are there indicators this domain is malicious or associated with threat activity?

### EEI-Driven Collection Steps

#### Step 1: WHOIS and Registration Information (PIR 1)

**EEIs**:
- Domain registrant name and organization
- Registrant email address and phone number
- Registration and expiration dates
- Domain registrar information
- Privacy protection status

**Collection Actions**:
```
1. Perform WHOIS lookup on target domain
   Tools: whois command line, ViewDNS.info, DomainTools

2. Check WHOIS history for changes over time
   Tools: DomainTools, SecurityTrails

3. Identify other domains registered by same registrant
   Tools: Reverse WHOIS (ViewDNS, DomainTools), RiskIQ

4. Note privacy protection services (may hide real registrant)
```

**Documentation**: Record all WHOIS data with timestamp, note privacy protections

#### Step 2: DNS and Network Infrastructure (PIR 2)

**EEIs**:
- Current A/AAAA records (IP addresses)
- MX records (email servers)
- NS records (nameservers)
- TXT records (SPF, DKIM, DMARC)
- Subdomain enumeration results
- ASN and network ownership
- Hosting provider information

**Collection Actions**:
```
1. Perform DNS lookups for all record types
   Tools: dig, nslookup, ViewDNS.info

2. Identify hosting provider and ASN
   Tools: WHOIS on IP, Shodan, IPinfo.io

3. Enumerate subdomains
   Tools: Sublist3r, Amass, crt.sh (certificate transparency)

4. Check passive DNS history
   Tools: SecurityTrails, VirusTotal, PassiveTotal (RiskIQ)

5. Identify related infrastructure (shared hosting, nameservers)
   Tools: Shodan reverse DNS, Bing IP: search
```

**Documentation**: Create infrastructure map showing domain → IP → hosting provider → ASN

#### Step 3: Historical Analysis (PIR 3)

**EEIs**:
- Domain age and first registration date
- Historical content (website snapshots)
- Historical DNS records
- Previous ownership or transfers
- Historical reputation scores

**Collection Actions**:
```
1. Check domain age and creation date
   Tools: WHOIS data

2. Review historical website content
   Tools: Wayback Machine (archive.org), Archive.today

3. Analyze historical DNS records
   Tools: SecurityTrails, PassiveTotal

4. Check historical reputation
   Tools: VirusTotal historical data, URLVoid

5. Identify significant changes (ownership, content, infrastructure)
```

**Documentation**: Timeline of significant domain events and changes

#### Step 4: Content and Service Analysis (PIR 4)

**EEIs**:
- Website content and purpose
- Technologies used (CMS, frameworks, libraries)
- Hosted services and applications
- SSL/TLS certificate information
- Open ports and services (for IP addresses)

**Collection Actions**:
```
1. Visit domain and document content (screenshot)
   Tools: Browser, Screenshot tools

2. Analyze web technologies
   Tools: BuiltWith, Wappalyzer, WhatWeb

3. Examine SSL/TLS certificate
   Tools: Browser inspection, crt.sh, Censys

4. Scan IP for open ports and services
   Tools: Shodan, Censys, nmap (if authorized)

5. Check for interesting files/directories
   Tools: Google dorks (site:domain.com), Archive.org
```

**Documentation**: Detailed description of content, screenshot, technology stack

#### Step 5: Reputation and Threat Assessment (PIR 5)

**EEIs**:
- Presence in threat intelligence feeds
- Blacklist status (spam, malware, phishing)
- Security vendor detections
- Community reports and discussions
- Associated malware samples
- Attribution to threat actors or campaigns

**Collection Actions**:
```
1. Check multi-source threat intelligence
   Tools: VirusTotal, AlienVault OTX, ThreatMiner

2. Verify blacklist status
   Tools: URLVoid, MXToolbox blacklist check

3. Search for security vendor reports
   Tools: Google search, Twitter/X, security blogs

4. Check for associated malware
   Tools: VirusTotal relations, Hybrid Analysis

5. Search for IOC mentions in threat reports
   Tools: Google, Twitter/X, threat intel platforms
```

**Documentation**: List all detections, blacklistings, and threat associations with sources

### IP Address Investigation Variant

For IP address investigations, adjust workflow:

**Additional EEIs for IP**:
- Geolocation data
- Autonomous System (AS) information
- Reverse DNS (PTR records)
- Open ports and services
- Hosted domains (virtual hosting)
- Network neighbors (adjacent IPs)

**Additional Collection Steps**:
```
1. Geolocate IP address
   Tools: IPinfo.io, MaxMind, IP2Location

2. Enumerate hosted domains (virtual hosts)
   Tools: Bing IP: search, Shodan reverse DNS, ViewDNS

3. Scan for open ports and services
   Tools: Shodan, Censys, BinaryEdge

4. Identify network neighbors
   Tools: Shodan, Censys (search by ASN or subnet)

5. Check for historical activity
   Tools: Shodan historical data, GreyNoise
```

### Domain/IP Investigation Checklist

- [ ] WHOIS lookup completed and documented
- [ ] DNS records enumerated (A, MX, NS, TXT)
- [ ] Subdomains identified
- [ ] Historical data reviewed (Wayback Machine, passive DNS)
- [ ] Hosting provider and ASN identified
- [ ] SSL/TLS certificate examined
- [ ] Website content documented (screenshot)
- [ ] Technologies identified (CMS, frameworks)
- [ ] Threat intelligence checked (VirusTotal, OTX)
- [ ] Blacklist status verified
- [ ] Related infrastructure mapped
- [ ] All PIRs answered with confidence levels assigned

---

## Workflow 2: Identity and Credential Investigation

### Use Cases
- Checking for compromised employee credentials
- Investigating suspicious individuals
- Assessing insider threat indicators
- Due diligence on persons of interest

### Sample PIRs for Identity Investigation

1. **PIR 1**: What online accounts and profiles are associated with this identity?
2. **PIR 2**: Has this identity's information appeared in data breaches or leaks?
3. **PIR 3**: What public information is available about this identity's activities and associations?
4. **PIR 4**: Are there indicators of suspicious or malicious activity by this identity?
5. **PIR 5**: What is the digital footprint and exposure risk of this identity?

### EEI-Driven Collection Steps

#### Step 1: Breach and Leak Database Search (PIR 2)

**EEIs**:
- Email addresses in breach databases
- Passwords (hashed or cleartext) in leaks
- Associated usernames in breaches
- Breach dates and affected services
- Additional personal information in breaches (phone, address, etc.)

**Collection Actions**:
```
1. Check email in breach databases
   Tools: HaveIBeenPwned, DeHashed, LeakCheck

2. Search for domain-wide breaches (for corporate investigations)
   Tools: DeHashed domain search, Intelligence X

3. Check for recent infostealer logs
   Tools: InfoStealers.info, LeakRadar

4. Search leak aggregation sites (carefully, may contain illegal data)
   Tools: COMB database search (where legal)

5. Document all breaches with dates and compromised data types
```

**Documentation**: Table of breaches with dates, services, compromised data fields

#### Step 2: Username and Account Enumeration (PIR 1)

**EEIs**:
- Social media profiles (Twitter, LinkedIn, Facebook, Instagram, etc.)
- Forum accounts and posts
- Professional accounts (GitHub, Stack Overflow, etc.)
- Gaming profiles (Steam, Xbox, PlayStation, etc.)
- Associated email addresses and alternate usernames

**Collection Actions**:
```
1. Search username across platforms
   Tools: WhatsMyName, Sherlock, Namechk

2. Check major social media manually
   Platforms: LinkedIn, Twitter/X, Facebook, Instagram, Reddit

3. Search professional developer platforms
   Tools: GitHub user search, GitLab, Stack Overflow

4. Check gaming and streaming platforms
   Platforms: Steam, Twitch, YouTube Gaming, Discord

5. Enumerate email variations
   Tools: Email permutator, EmailHippo
```

**Documentation**: Spreadsheet of accounts with platform, username, profile URL, last activity date

#### Step 3: Social Media Intelligence Collection (PIR 3)

**EEIs**:
- Public posts and content
- Connections and relationships (followers, friends, professional contacts)
- Location and travel information
- Employment and education history
- Interests and affiliations
- Timeline of activities

**Collection Actions**:
```
1. Review public social media posts
   Tools: Platform native search, Google site: searches

2. Analyze social connections
   Tools: LinkedIn connections, Twitter followers, Facebook friends list

3. Extract metadata from posts
   Tools: EXIF data from images, geolocation from check-ins

4. Timeline major life events and job changes
   Tools: LinkedIn history, Facebook timeline, Twitter archive

5. Identify affiliations (groups, organizations, causes)
   Tools: LinkedIn groups, Facebook groups, Meetup.com
```

**Documentation**: Profile summary with timeline, key connections, significant posts (screenshots)

#### Step 4: Public Records and Online Presence (PIR 3, PIR 5)

**EEIs**:
- Domain registrations under identity's name
- Business registrations and filings
- Public records (where legal to access)
- Publications and media mentions
- Certifications and credentials

**Collection Actions**:
```
1. Reverse WHOIS search by name/email
   Tools: ViewDNS reverse WHOIS, DomainTools

2. Search for mentions in news and media
   Tools: Google News, Bing News, news aggregators

3. Check for academic publications
   Tools: Google Scholar, ResearchGate, Academia.edu

4. Search business registrations (where available)
   Tools: State/country business registries

5. Look for professional certifications
   Tools: Certification verification sites (depends on field)
```

**Documentation**: List of public mentions, publications, affiliations, domains

#### Step 5: Threat Indicator Assessment (PIR 4)

**EEIs**:
- Presence in threat actor databases
- Mentions in security forums or darknet
- Credential selling or sharing activity
- Malicious infrastructure ownership
- Association with known threat actors

**Collection Actions**:
```
1. Search for identity in threat intelligence platforms
   Tools: AlienVault OTX, MISP communities (if access)

2. Check underground forum membership (carefully)
   Tools: Google searches for username + "forum"

3. Look for identity in malware samples or configs
   Tools: VirusTotal, Hybrid Analysis (search by email/username)

4. Check for credential selling activity
   Tools: Search markets mentioned in threat reports (carefully)

5. Review security community discussions
   Tools: Twitter/X security researchers, Reddit r/netsec
```

**Documentation**: Any threat indicators found, with context and severity assessment

### Identity Investigation Checklist

- [ ] All email addresses checked in breach databases
- [ ] Username enumeration across major platforms completed
- [ ] Social media profiles identified and reviewed
- [ ] Public posts and content documented (key screenshots)
- [ ] Social connections mapped (key relationships identified)
- [ ] Reverse WHOIS performed
- [ ] Public records and mentions searched
- [ ] Threat indicators assessed
- [ ] Digital footprint exposure summarized
- [ ] All PIRs answered with confidence levels

---

## Workflow 3: Threat Actor Profiling

### Use Cases
- Building profiles of new or emerging threat actors
- Tracking threat actor infrastructure and activity
- Attributing attacks to known groups
- Assessing threat actor capabilities and intentions

### Sample PIRs for Threat Actor Investigation

1. **PIR 1**: What infrastructure (domains, IPs, certificates) is associated with this threat actor?
2. **PIR 2**: What TTPs (tools, techniques, procedures) does this threat actor employ?
3. **PIR 3**: What industries, geographies, or organizations does this threat actor target?
4. **PIR 4**: What is the timeline and evolution of this threat actor's activities?
5. **PIR 5**: How is this threat actor attributed and what are confidence levels?

### EEI-Driven Collection Steps

#### Step 1: Threat Intelligence Aggregation (PIR 1, PIR 2, PIR 5)

**EEIs**:
- Published IOCs (domains, IPs, hashes, URLs)
- Attributed campaigns and operations
- Known tools and malware families
- MITRE ATT&CK technique mappings
- Aliases and naming conventions
- Attribution statements from vendors

**Collection Actions**:
```
1. Search threat intelligence platforms
   Tools: AlienVault OTX, MISP, ThreatMiner, ThreatCrowd

2. Review security vendor blogs and reports
   Sources: CrowdStrike, FireEye/Mandiant, Kaspersky, ESET, etc.

3. Search for MITRE ATT&CK group profile
   Tool: attack.mitre.org (Groups section)

4. Aggregate IOCs from multiple sources
   Tools: IOC extraction from PDFs, manual collection

5. Search Twitter/X security researcher discussions
   Tools: Twitter advanced search, TweetDeck
```

**Documentation**: Threat actor dossier with aliases, attribution, known IOCs, TTPs

#### Step 2: Infrastructure Tracking (PIR 1)

**EEIs**:
- Current and historical domains
- Current and historical IP addresses
- SSL/TLS certificate patterns
- Autonomous systems (ASNs) used
- Hosting providers preferred
- Domain registration patterns

**Collection Actions**:
```
1. Enumerate known infrastructure from threat reports
   Process: Extract IOCs from reports

2. Pivot on infrastructure patterns
   - Certificate commonalities (crt.sh, Censys)
   - WHOIS patterns (registrant email, name)
   - Hosting patterns (ASN, provider)
   Tools: PassiveTotal, SecurityTrails, Shodan, Censys

3. Check passive DNS for infrastructure relationships
   Tools: SecurityTrails, VirusTotal relationships

4. Monitor for new infrastructure
   Tools: Certificate transparency monitoring, DNS monitoring

5. Map infrastructure clusters and relationships
   Tools: Maltego, visualization tools, manual graphing
```

**Documentation**: Infrastructure map/graph showing relationships, timeline of infrastructure use

#### Step 3: TTP and Capability Analysis (PIR 2)

**EEIs**:
- Malware families used
- Exploit techniques and vulnerabilities exploited
- Initial access methods
- Lateral movement techniques
- Persistence mechanisms
- Exfiltration methods
- Tools and frameworks used

**Collection Actions**:
```
1. Collect malware samples associated with actor
   Tools: VirusTotal, Hybrid Analysis, malware repositories

2. Analyze TTPs from incident reports
   Process: Extract techniques from reports, map to MITRE ATT&CK

3. Identify exploit usage (CVEs exploited)
   Tools: Search reports for CVE mentions, exploit databases

4. Document tool usage
   Tools: Search for custom tools, open-source tool adoption

5. Assess technical sophistication
   Analysis: Review complexity of tools and techniques
```

**Documentation**: TTP matrix (MITRE ATT&CK format), malware family list, capability assessment

#### Step 4: Targeting Analysis (PIR 3)

**EEIs**:
- Industries targeted (sectors)
- Geographic focus (countries, regions)
- Organization types targeted
- Victim profiles
- Campaign objectives
- Motivations (financial, espionage, disruption, etc.)

**Collection Actions**:
```
1. Extract targeting information from reports
   Process: Review incident reports for victim details

2. Analyze victim patterns
   Analysis: Identify commonalities in victims

3. Assess motivations based on actions
   Analysis: Theft (financial), espionage (data), disruption (destruction)

4. Map to geopolitical context
   Analysis: Align activity with geopolitical events (if nation-state)

5. Predict future targeting
   Analysis: Extrapolate from historical patterns
```

**Documentation**: Targeting profile with industry breakdown, geographic map, motivation assessment

#### Step 5: Timeline and Evolution (PIR 4)

**EEIs**:
- First observed activity date
- Major campaigns and operations timeline
- Tool and technique evolution over time
- Infrastructure changes over time
- Attribution evolution (discovery to attribution)

**Collection Actions**:
```
1. Create activity timeline from reports
   Process: Extract dates from all collected reports

2. Document major campaigns chronologically
   Tools: Timeline visualization tools

3. Track tool/technique evolution
   Analysis: How have capabilities changed over time?

4. Note infrastructure rotation patterns
   Analysis: How often does actor change infrastructure?

5. Document attribution confidence changes
   Process: Track how attribution solidified over time
```

**Documentation**: Visual timeline of threat actor activity with key milestones

### Threat Actor Profiling Checklist

- [ ] Threat intelligence platforms searched
- [ ] Security vendor reports collected
- [ ] IOCs aggregated from all sources
- [ ] Infrastructure enumerated and mapped
- [ ] Passive DNS and certificate pivots performed
- [ ] Malware samples identified
- [ ] TTPs mapped to MITRE ATT&CK
- [ ] Targeting patterns analyzed
- [ ] Timeline of activity created
- [ ] Attribution assessed with confidence levels
- [ ] All PIRs answered

---

## Workflow 4: Malware and IOC Analysis

### Use Cases
- Analyzing suspicious files or URLs
- Investigating indicators of compromise (IOCs)
- Tracking malware campaigns
- Building detection and response capabilities

### Sample PIRs for Malware Investigation

1. **PIR 1**: What is the functionality and behavior of this malware?
2. **PIR 2**: What infrastructure is associated with this malware (C2, delivery, etc.)?
3. **PIR 3**: What threat actor or campaign is this malware attributed to?
4. **PIR 4**: How widespread is this malware and what is its impact?
5. **PIR 5**: What detections and mitigations are available?

### EEI-Driven Collection Steps

#### Step 1: Initial Malware Triage (PIR 1)

**EEIs**:
- File hash (MD5, SHA1, SHA256)
- File type and format
- File size
- Compilation timestamp
- Packer or obfuscation indicators
- Basic static analysis results

**Collection Actions**:
```
1. Calculate file hashes
   Tools: md5sum, sha256sum, or file property tools

2. Check file type
   Tools: file command (Linux), TrID

3. Search hash in malware databases
   Tools: VirusTotal, Hybrid Analysis, MalwareBazaar

4. Check for packing/obfuscation
   Tools: PEiD, Detect It Easy (DiE)

5. Review VirusTotal detections
   Analysis: How many AV vendors detect? What names?
```

**Documentation**: Malware quick facts sheet (hashes, type, detection ratio, names)

#### Step 2: Behavioral Analysis via Sandboxing (PIR 1)

**EEIs**:
- Network communications (domains, IPs contacted)
- File system modifications
- Registry modifications (Windows)
- Process creation and injection
- API calls
- Persistence mechanisms
- Indicators of compromise generated

**Collection Actions**:
```
1. Submit to online sandboxes (if safe to do so)
   Tools: Hybrid Analysis, Any.Run, Joe Sandbox, Triage

2. Review behavioral analysis reports
   Analysis: What does the malware do when executed?

3. Extract IOCs from sandbox reports
   Process: Domains, IPs, file hashes, registry keys

4. Identify C2 communication patterns
   Analysis: How does malware communicate with C2?

5. Document persistence methods
   Analysis: How does malware maintain access?
```

**Documentation**: Behavioral summary, IOC list, C2 communication details

#### Step 3: Infrastructure Investigation (PIR 2)

**EEIs**:
- Command and control (C2) domains and IPs
- Distribution infrastructure (phishing domains, exploit kit domains)
- Exfiltration infrastructure
- Historical infrastructure usage
- Infrastructure patterns and relationships

**Collection Actions**:
```
1. Extract network IOCs from sandbox reports
   Process: List all domains and IPs contacted

2. Investigate C2 infrastructure
   Process: Use Domain/IP workflow on each C2 indicator

3. Check passive DNS for infrastructure relationships
   Tools: SecurityTrails, VirusTotal

4. Identify hosting patterns
   Analysis: Shared hosting, bulletproof hosting, legitimate cloud?

5. Search for related samples using same infrastructure
   Tools: VirusTotal relationships, RiskIQ
```

**Documentation**: Infrastructure map showing C2 servers, distribution points, relationships

#### Step 4: Attribution and Campaign Linkage (PIR 3, PIR 4)

**EEIs**:
- Malware family identification
- Attribution to threat actors
- Associated campaigns
- Similar samples (variants)
- Distribution vector (phishing, drive-by, etc.)

**Collection Actions**:
```
1. Identify malware family name
   Tools: VirusTotal naming, YARA rule matches, expert analysis

2. Search for attribution in threat reports
   Tools: Google search for malware family name, Twitter/X

3. Find similar samples
   Tools: VirusTotal similar files, Hybrid Analysis, RetroHunt

4. Identify distribution campaigns
   Tools: URLhaus, PhishTank, threat reports

5. Link to threat actor (if possible)
   Analysis: Does infrastructure or TTPs match known actor?
```

**Documentation**: Attribution assessment with evidence, campaign timeline, similar samples

#### Step 5: Detection and Mitigation Research (PIR 5)

**EEIs**:
- YARA rules for detection
- Snort/Suricata signatures
- SIGMA rules for log-based detection
- Mitigation recommendations
- Removal/remediation procedures
- Vulnerability exploited (if exploit-based)

**Collection Actions**:
```
1. Search for detection rules
   Sources: GitHub YARA repos, Sigma HQ, security vendor rules

2. Identify exploited vulnerabilities
   Tools: Check reports, sandbox analysis for exploit behavior

3. Research mitigation guidance
   Sources: CISA advisories, vendor security bulletins

4. Find remediation procedures
   Sources: Antivirus vendor removal guides, SANS, US-CERT

5. Check for decryptors (if ransomware)
   Tools: No More Ransom project, vendor decryptor releases
```

**Documentation**: Detection rules, mitigation steps, remediation procedures

### Malware Analysis Checklist

- [ ] File hashes calculated and searched
- [ ] VirusTotal analysis reviewed
- [ ] Sandbox analysis completed
- [ ] Behavioral IOCs extracted
- [ ] C2 infrastructure investigated
- [ ] Related samples identified
- [ ] Malware family identified
- [ ] Attribution assessed
- [ ] Distribution campaign documented
- [ ] Detection rules collected
- [ ] Mitigation guidance researched
- [ ] All PIRs answered

---

## Workflow 5: Social Media Intelligence (SOCMINT)

### Use Cases
- Monitoring threat actor social media presence
- Tracking disinformation campaigns
- Assessing public sentiment about security events
- Identifying insider threats or leaks

### Sample PIRs for SOCMINT Investigation

1. **PIR 1**: What accounts and personas is the target using on social media?
2. **PIR 2**: What content is the target posting and what does it reveal?
3. **PIR 3**: Who is the target connected to and communicating with?
4. **PIR 4**: What patterns exist in the target's social media activity?
5. **PIR 5**: Are there indicators of intent, capability, or opportunity for malicious activity?

### EEI-Driven Collection Steps

#### Step 1: Account Discovery and Enumeration (PIR 1)

**EEIs**:
- Social media accounts across platforms
- Usernames and handles
- Profile information (bio, location, etc.)
- Account creation dates
- Verification status
- Associated accounts (linked profiles)

**Collection Actions**:
```
1. Search username across platforms
   Tools: WhatsMyName, Sherlock, Namechk

2. Use platform native search
   Platforms: Twitter/X, Facebook, LinkedIn, Instagram, Reddit, etc.

3. Check profile linking
   Process: Many users link their other social accounts in profiles

4. Search for mentions of the target
   Tools: Platform search, Google site: searches

5. Identify alternate personas
   Analysis: Look for references to "alt accounts" or pseudonyms
```

**Documentation**: Account inventory with platforms, handles, profile URLs, status

#### Step 2: Content Analysis (PIR 2)

**EEIs**:
- Post content (text, images, videos, links)
- Post frequency and timing
- Topics and themes discussed
- Sentiment and tone
- Language and communication style
- Metadata (locations, timestamps)

**Collection Actions**:
```
1. Review recent posts manually
   Tools: Platform interfaces, screenshots

2. Analyze post frequency and timing
   Analysis: When is target most active? Timezone indicators?

3. Identify key topics and themes
   Analysis: What does target discuss most? Any patterns?

4. Extract metadata from images
   Tools: ExifTool, online EXIF viewers

5. Analyze links shared
   Process: Where does target share links to? What sources?
```

**Documentation**: Content summary with themes, sample posts (screenshots), metadata findings

#### Step 3: Network Analysis (PIR 3)

**EEIs**:
- Followers and following lists
- Connections (friends, professional connections)
- Interaction patterns (who does target engage with?)
- Group memberships
- Tagging and mentions
- Direct communication indicators

**Collection Actions**:
```
1. Export follower/following lists (where possible)
   Tools: Platform APIs, Twitter archiving tools

2. Identify key connections
   Analysis: Who does target interact with most frequently?

3. Check group memberships
   Platforms: Facebook groups, LinkedIn groups, Reddit communities

4. Analyze mention patterns
   Analysis: Who mentions the target? Who does target mention?

5. Look for coordination indicators
   Analysis: Synchronized posting, similar content across accounts
```

**Documentation**: Network diagram or list of key connections, interaction summary

#### Step 4: Pattern and Anomaly Detection (PIR 4)

**EEIs**:
- Posting patterns over time
- Topic evolution
- Behavior changes
- Anomalous activity
- Location patterns (if shared)
- Device and platform usage

**Collection Actions**:
```
1. Create timeline of social media activity
   Tools: Timeline visualization, spreadsheet analysis

2. Identify significant changes
   Analysis: Changes in posting frequency, tone, topics

3. Detect anomalies
   Analysis: Unusual posts, account compromises, suspicious links

4. Track location mentions
   Analysis: Where does target claim to be or travel?

5. Assess operational security
   Analysis: Does target leak sensitive information?
```

**Documentation**: Timeline visualization, pattern summary, anomaly log

#### Step 5: Threat Indicator Assessment (PIR 5)

**EEIs**:
- Expressions of intent (threats, plans)
- Capability indicators (skills, tools, access)
- Opportunity indicators (target knowledge, timing)
- Concerning communications
- Association with known threats
- Radicalization or recruitment indicators

**Collection Actions**:
```
1. Search for concerning keywords and phrases
   Process: Threats, weapons, attack planning terms (context-dependent)

2. Assess technical capability
   Analysis: Does target demonstrate cyber skills? Access?

3. Identify opportunity indicators
   Analysis: Does target have access or knowledge to conduct attacks?

4. Review associations
   Analysis: Is target connected to known threat actors?

5. Consult threat frameworks
   Framework: Apply threat assessment models (if trained)
```

**Documentation**: Threat assessment summary with specific concerning indicators

### SOCMINT Investigation Checklist

- [ ] All social media platforms searched for accounts
- [ ] Accounts enumerated and documented
- [ ] Recent posts reviewed and sampled
- [ ] Content themes identified
- [ ] Image metadata extracted
- [ ] Follower/following lists analyzed
- [ ] Key connections identified
- [ ] Interaction patterns documented
- [ ] Activity timeline created
- [ ] Anomalies or behavior changes noted
- [ ] Threat indicators assessed
- [ ] All PIRs answered

**⚠️ LEGAL AND ETHICAL NOTE**: Always ensure SOCMINT activities comply with applicable laws, platform terms of service, and organizational policies. Avoid impersonation, unauthorized access, or harassment.

---

## Workflow 6: Supply Chain and Third-Party Risk Assessment

### Use Cases
- Vetting new vendors and partners
- Assessing third-party security posture
- Investigating supply chain compromises
- Evaluating software dependencies

### Sample PIRs for Supply Chain Investigation

1. **PIR 1**: What is the external attack surface of this vendor/supplier?
2. **PIR 2**: What security incidents or breaches has this vendor experienced?
3. **PIR 3**: What vulnerabilities exist in this vendor's products or services?
4. **PIR 4**: How does this vendor's security posture compare to industry standards?
5. **PIR 5**: What third-party and fourth-party risks exist in this vendor's supply chain?

### EEI-Driven Collection Steps

#### Step 1: External Attack Surface Mapping (PIR 1)

**EEIs**:
- Owned domains and subdomains
- External IP ranges
- Exposed services and ports
- Cloud infrastructure usage
- Web applications and APIs
- Email infrastructure
- Employee exposure (credential leaks)

**Collection Actions**:
```
1. Enumerate vendor domains
   Tools: Certificate transparency (crt.sh), subdomain enumeration

2. Identify IP ranges and ASNs
   Tools: WHOIS on primary domain, BGP data, Shodan

3. Scan for exposed services
   Tools: Shodan, Censys, BinaryEdge

4. Identify web applications and APIs
   Tools: Subdomain enum results, BuiltWith, Wappalyzer

5. Check for employee credential exposure
   Tools: DeHashed domain search, HaveIBeenPwned
```

**Documentation**: Attack surface inventory with asset counts, exposed services

#### Step 2: Incident and Breach History (PIR 2)

**EEIs**:
- Historical security incidents
- Data breaches disclosed
- Ransomware attacks
- Regulatory actions or fines
- Lawsuit filings related to security
- Media reports of security issues

**Collection Actions**:
```
1. Search for breach disclosures
   Tools: Google News, Privacy Rights Clearinghouse, databreaches.net

2. Check breach databases
   Tools: HaveIBeenPwned (domain search), DeHashed

3. Search regulatory filings
   Sources: SEC filings (if public company), GDPR fine databases

4. Review security news
   Tools: Google News search for vendor + "breach" or "hack"

5. Check lawsuit databases
   Sources: PACER (US), legal news sites
```

**Documentation**: Incident history timeline with severity and response assessment

#### Step 3: Product Vulnerability Assessment (PIR 3)

**EEIs**:
- CVEs assigned to vendor products
- Security advisories published by vendor
- Third-party vulnerability disclosures
- Patch frequency and response time
- Presence of bug bounty program
- Software supply chain vulnerabilities (dependencies)

**Collection Actions**:
```
1. Search CVE databases
   Tools: CVE.org, NVD, vendor security advisories

2. Review vendor security bulletins
   Sources: Vendor website security section

3. Check for bug bounty program
   Sources: HackerOne, Bugcrowd, vendor website

4. Analyze patch response times
   Analysis: How quickly does vendor patch critical issues?

5. Check software dependencies (if software vendor)
   Tools: GitHub dependency graphs, Snyk, npm audit
```

**Documentation**: Vulnerability summary with CVE counts by severity, patching practices

#### Step 4: Security Posture Assessment (PIR 4)

**EEIs**:
- Security certifications (ISO 27001, SOC 2, etc.)
- Compliance attestations
- Published security documentation
- Security team presence (job postings, conference talks)
- Participation in security community
- Security tooling and technologies used

**Collection Actions**:
```
1. Check for security certifications
   Sources: Vendor website, trust pages, compliance databases

2. Review public security documentation
   Sources: Vendor security whitepapers, trust center

3. Assess security team maturity
   Analysis: LinkedIn search for vendor security employees

4. Check security conference participation
   Tools: Search conference attendee lists, YouTube talks

5. Identify security tooling
   Tools: BuiltWith, Wappalyzer, job postings mentioning tools
```

**Documentation**: Security maturity scorecard with certifications, practices

#### Step 5: Fourth-Party Risk Analysis (PIR 5)

**EEIs**:
- Vendor's own suppliers and dependencies
- Cloud providers used by vendor
- Open-source dependencies in vendor products
- Outsourced or offshore operations
- Data storage locations
- Subprocessor disclosures (for data processors)

**Collection Actions**:
```
1. Review vendor subprocessor lists
   Sources: Vendor website (GDPR requirement), privacy policies

2. Identify cloud infrastructure providers
   Tools: Netcraft, Shodan, BuiltWith

3. Enumerate software dependencies
   Tools: GitHub, npm, PyPI (if open-source components)

4. Research vendor's supply chain
   Sources: Vendor website (partners page), press releases

5. Identify data storage locations
   Sources: Privacy policy, data processing agreements
```

**Documentation**: Fourth-party risk map showing vendor's suppliers and dependencies

### Supply Chain Risk Assessment Checklist

- [ ] Vendor domains and subdomains enumerated
- [ ] External IP ranges identified
- [ ] Exposed services cataloged
- [ ] Historical incidents researched
- [ ] Breach history documented
- [ ] CVEs for vendor products reviewed
- [ ] Security certifications verified
- [ ] Security maturity assessed
- [ ] Vendor's suppliers identified (fourth-party risk)
- [ ] Overall risk rating assigned
- [ ] All PIRs answered

---

## Workflow 7: Critical Infrastructure Threat Assessment

### Use Cases
- Assessing threats to ICS/SCADA systems
- Evaluating vulnerabilities in operational technology
- Monitoring threats to critical sectors (energy, water, transportation)
- Investigating cyber-physical attacks

### Sample PIRs for Critical Infrastructure Investigation

1. **PIR 1**: What threat actors have the capability and intent to target our critical infrastructure sector?
2. **PIR 2**: What vulnerabilities exist in the ICS/OT systems we operate?
3. **PIR 3**: What attacks or incidents have targeted similar infrastructure?
4. **PIR 4**: What threat intelligence exists for our specific infrastructure vendors and technologies?
5. **PIR 5**: What indicators should we monitor for threats to our infrastructure?

### EEI-Driven Collection Steps

#### Step 1: Threat Actor Identification (PIR 1)

**EEIs**:
- Nation-state actors targeting critical infrastructure
- Hacktivist groups with infrastructure focus
- Cybercriminal groups (ransomware, extortion)
- Insider threat indicators
- Historical attacks on infrastructure sector

**Collection Actions**:
```
1. Research nation-state cyber programs
   Sources: Government threat assessments, intelligence reports

2. Identify sector-specific threat actors
   Tools: MITRE ATT&CK for ICS, threat intel platforms

3. Review ICS-CERT advisories
   Source: CISA ICS-CERT (ics-cert.us-cert.gov)

4. Search for hacktivist targeting
   Tools: Twitter/X, hacktivist announcement channels

5. Review ransomware targeting of infrastructure
   Sources: Ransomware tracking sites, incident reports
```

**Documentation**: Threat actor list with capabilities, intent, historical activity

#### Step 2: Vulnerability Intelligence for ICS/OT (PIR 2)

**EEIs**:
- CVEs for ICS/SCADA products used
- Vendor security advisories
- ICS-CERT vulnerability alerts
- Zero-day exploits targeting OT
- Protocol vulnerabilities (Modbus, DNP3, etc.)
- Configuration weaknesses

**Collection Actions**:
```
1. Search ICS vulnerability databases
   Tools: ICS-CERT advisories, NVD (filter for ICS), ICS-specific CVE searches

2. Review vendor security bulletins
   Sources: Siemens, Schneider Electric, Rockwell, etc. security pages

3. Monitor ICS security research
   Sources: BlackHat/DEF CON ICS Village, S4 Conference talks

4. Check for exploit availability
   Tools: GitHub, Exploit-DB, Metasploit modules

5. Research protocol vulnerabilities
   Sources: Academic papers, security conference presentations
```

**Documentation**: Vulnerability matrix with CVEs, affected systems, exploit availability

#### Step 3: Incident and Attack Pattern Research (PIR 3)

**EEIs**:
- Historical attacks on similar infrastructure
- Attack vectors used in ICS compromises
- TTPs specific to ICS/OT environments
- Malware families targeting ICS (Stuxnet, TRITON, etc.)
- Lessons learned from past incidents

**Collection Actions**:
```
1. Research major ICS incidents
   Examples: Stuxnet, BlackEnergy, TRITON, Industroyer

2. Review NIST/CISA case studies
   Sources: CISA incident reports, NIST publications

3. Analyze ICS-specific TTPs
   Tool: MITRE ATT&CK for ICS framework

4. Study ICS malware families
   Tools: VirusTotal, malware analysis reports

5. Extract lessons learned
   Analysis: What could prevent similar attacks?
```

**Documentation**: Incident case study summaries, attack pattern catalog

#### Step 4: Vendor and Technology Threat Intelligence (PIR 4)

**EEIs**:
- Vulnerabilities in specific vendors/products used
- Threat actor interest in our vendors
- Supply chain risks for our vendors
- Updates and patch schedules
- Vendor security response capabilities

**Collection Actions**:
```
1. Create inventory of ICS vendors and products
   Process: Document all OT systems and versions

2. Search vulnerabilities by vendor and product
   Tools: NVD, ICS-CERT, vendor security pages

3. Check threat intel for vendor targeting
   Tools: VirusTotal, threat intel platforms

4. Review vendor security practices
   Analysis: Does vendor have a PSIRT? Response SLAs?

5. Monitor vendor security announcements
   Process: Subscribe to vendor security mailing lists
```

**Documentation**: Vendor risk profile for each major ICS vendor used

#### Step 5: Detection and Monitoring Strategy (PIR 5)

**EEIs**:
- IOCs for ICS-targeting malware
- Network monitoring signatures for ICS attacks
- Log sources and detection rules
- Baseline normal behavior for OT systems
- ICS-specific detection tools

**Collection Actions**:
```
1. Collect IOCs for ICS threats
   Sources: ICS-CERT, threat intel sharing communities

2. Identify ICS detection rules
   Tools: Snort/Suricata ICS rules, SIGMA rules for ICS

3. Research ICS monitoring tools
   Tools: Dragos, Nozomi, Claroty, Darktrace for OT

4. Define normal OT behavior
   Process: Document expected protocols, traffic patterns

5. Plan detection coverage
   Analysis: What log sources are needed? What visibility gaps exist?
```

**Documentation**: Detection strategy document with IOCs, rules, monitoring plan

### Critical Infrastructure Assessment Checklist

- [ ] Relevant threat actors identified and profiled
- [ ] ICS/OT vulnerabilities cataloged
- [ ] Historical incidents researched
- [ ] Sector-specific threats documented
- [ ] Vendor-specific intelligence gathered
- [ ] IOCs for ICS threats collected
- [ ] Detection and monitoring strategy developed
- [ ] Risk assessment completed
- [ ] Mitigation recommendations provided
- [ ] All PIRs answered

---

## Workflow 8: Identity Surface Investigation (Human and Non-Human)

### Use Cases
- Assessing exposure of human identities (employees, users)
- Discovering compromised non-human identities (NHIDs)
- Investigating identity-based attacks
- Evaluating identity management security

### Sample PIRs for Identity Investigation

1. **PIR 1**: What human identities (employees, privileged users) are exposed or compromised?
2. **PIR 2**: What non-human identities (service accounts, API keys, tokens) are publicly exposed?
3. **PIR 3**: What identity infrastructure vulnerabilities exist in our environment?
4. **PIR 4**: What threat actors specifically target identity systems and credentials?
5. **PIR 5**: What detection and response capabilities exist for identity-based attacks?

### EEI-Driven Collection Steps

#### Step 1: Human Identity Exposure Assessment (PIR 1)

**EEIs**:
- Employee email addresses in breach databases
- Employee credentials in leaks or darknet markets
- Employee social media exposure
- Privileged account information leakage
- Employee accounts on underground forums

**Collection Actions**:
```
1. Enumerate employee email addresses
   Sources: LinkedIn, company website, email permutation

2. Check breaches for all employee emails
   Tools: HaveIBeenPwned, DeHashed, LeakCheck

3. Search for corporate domain in leak databases
   Tools: DeHashed domain search, Intelligence X

4. Check for employee accounts on underground forums
   Process: Search major forums for corporate email addresses (carefully)

5. Assess privileged user exposure specifically
   Focus: Admin accounts, developers, executives
```

**Documentation**: Exposure report with compromised accounts, breach details, severity

#### Step 2: Non-Human Identity (NHID) Discovery (PIR 2)

**EEIs**:
- API keys in public repositories
- Service account credentials exposed
- OAuth tokens leaked
- Cloud service principal credentials
- CI/CD pipeline secrets
- Database connection strings
- Certificate and key material

**Collection Actions**:
```
1. Scan GitHub for exposed secrets
   Tools: GitHub secret scanning, TruffleHog, GitLeaks

2. Search paste sites for credentials
   Tools: Pastebin, GitHub Gists, Ghostbin searches

3. Check for .env files in public repos
   Tools: GitHub code search for "db_password", "api_key", etc.

4. Search for AWS keys, Azure tokens
   Process: GitHub search for "AKIA", "Azure", etc.

5. Monitor certificate transparency logs
   Tools: crt.sh for organization certificates
```

**Documentation**: NHID exposure report with credentials found, exposure severity, remediation status

#### Step 3: Identity Infrastructure Assessment (PIR 3)

**EEIs**:
- Active Directory exposure (external authentication portals)
- Identity provider misconfigurations
- SAML and OAuth vulnerabilities
- MFA adoption and bypass opportunities
- Password policy weaknesses
- Certificate authority security

**Collection Actions**:
```
1. Identify externally-facing identity services
   Tools: Shodan, Censys (search for "OWA", "AD FS", "Okta", etc.)

2. Check for identity misconfiguration research
   Sources: Security research on Azure AD, AWS IAM, Okta, etc.

3. Review authentication security advisories
   Sources: CISA, vendor security bulletins

4. Assess password policy strength
   Analysis: Review corporate password policy documentation

5. Check for certificate vulnerabilities
   Tools: SSL Labs, certificate transparency logs
```

**Documentation**: Identity infrastructure security assessment with findings

#### Step 4: Identity-Focused Threat Actor Research (PIR 4)

**EEIs**:
- Threat actors focused on credential theft
- Phishing campaigns targeting identities
- Golden/Silver ticket attacks
- Pass-the-hash and pass-the-ticket techniques
- MFA bypass methods
- Identity provider exploits

**Collection Actions**:
```
1. Research identity-focused threat actors
   Sources: Threat intel reports, MITRE ATT&CK (Credential Access)

2. Track phishing campaigns
   Tools: PhishTank, OpenPhish, anti-phishing working group

3. Study Active Directory attack techniques
   Sources: Red team blogs, Bloodhound research, ADSecurity.org

4. Monitor for MFA bypass techniques
   Sources: Security researcher blogs, conference talks

5. Review identity exploit techniques
   Tool: MITRE ATT&CK Technique T1078 (Valid Accounts) and related
```

**Documentation**: Threat landscape summary for identity attacks

#### Step 5: Detection and Response for Identity Threats (PIR 5)

**EEIs**:
- Log sources for identity events
- Detection rules for credential abuse
- Anomaly detection capabilities
- Incident response procedures for identity compromise
- Identity monitoring tools

**Collection Actions**:
```
1. Identify identity log sources
   Examples: AD logs, Azure AD logs, IAM logs, auth logs

2. Research detection rules for identity attacks
   Tools: SIGMA rules, Splunk security content, Elastic rules

3. Evaluate anomaly detection capabilities
   Tools: UEBA tools, Microsoft Defender for Identity, Varonis

4. Review identity incident response playbooks
   Sources: NIST, SANS, internal runbooks

5. Assess identity monitoring tools
   Tools: Bloodhound, PingCastle, Purple Knight
```

**Documentation**: Identity detection and response capability assessment

### Identity Surface Investigation Checklist

- [ ] Employee emails enumerated
- [ ] Breach exposure checked for all employees
- [ ] Privileged accounts specifically assessed
- [ ] GitHub and code repositories scanned for secrets
- [ ] Paste sites searched for credentials
- [ ] Non-human identities (API keys, tokens) enumerated
- [ ] Identity infrastructure mapped (AD, IdP, etc.)
- [ ] Identity-focused threat actors researched
- [ ] Detection capabilities for identity attacks assessed
- [ ] Response procedures reviewed
- [ ] All PIRs answered

---

## Using Intelligence Requirements in Workflows

### Applying the CIR → CIN → PIR → EEI Cascade

Every workflow in this document follows the intelligence requirements framework:

**Strategic Level (CIR/CIN)**: Each workflow addresses a Critical Intelligence Need derived from broader CIRs
- Example: CIR "What are active threats to our enterprise?" → CIN "Threat actors targeting our technology stack"

**Operational Level (PIR)**: Workflows are structured around PIRs
- Example: "What domains and IP addresses is threat actor X currently using?"

**Tactical Level (EEI)**: Collection steps are EEIs
- Example: "Domain names associated with threat actor X in the past 90 days"

**Benefits**:
- **Traceability**: Every collection action traces to a strategic requirement
- **Efficiency**: Avoid collecting irrelevant information
- **Completeness**: EEIs ensure comprehensive coverage
- **Reporting**: Answer PIRs systematically

### Adapting Workflows to Your Requirements

To adapt these workflows:

1. **Start with your CIRs**: What are your organization's critical intelligence requirements?
2. **Derive CINs**: Break CIRs into intelligence topic areas
3. **Formulate PIRs**: Write specific questions you need to answer
4. **Map to workflows**: Which workflows address your PIRs?
5. **Customize EEIs**: Adjust collection steps to your specific targets and environment
6. **Execute**: Follow the workflow systematically
7. **Document**: Use the templates provided
8. **Refine**: Update requirements based on findings

---

## Workflow Documentation Templates

### Template 1: Investigation Summary

```markdown
# Investigation Summary

**Investigation ID**: [Unique ID]
**Date**: [Start Date] - [End Date]
**Investigator(s)**: [Names]
**Investigation Type**: [Workflow Used]

## Target Information
- **Target**: [Person/Domain/IP/Organization/Threat Actor]
- **Context**: [Why this investigation was initiated]
- **Priority**: [Critical/High/Medium/Low]

## Priority Intelligence Requirements (PIRs)

### PIR 1: [Question]
**Status**: [Answered/Partially Answered/Unable to Answer]
**Answer**: [Detailed answer with evidence]
**Confidence Level**: [High/Medium/Low]
**Sources Used**: [List of sources]
**Gaps**: [Any information gaps]

### PIR 2: [Question]
[Repeat structure]

## Key Findings
1. [Finding with supporting evidence]
2. [Finding with supporting evidence]
3. [Finding with supporting evidence]

## Intelligence Gaps
- [PIRs not fully answered]
- [Missing information]
- [Reasons gaps exist]

## Recommendations
- [Actionable recommendations based on findings]

## Follow-on Requirements
- [New PIRs generated from this investigation]
- [Areas requiring deeper investigation]

## Appendices
- [Attached evidence files]
- [Screenshots]
- [Raw data exports]
```

### Template 2: Collection Log

```markdown
# OSINT Collection Log

**Investigation ID**: [ID]
**Date**: [Date]

| Time | Source/Tool | EEI Addressed | Query/Action | Findings | Notes |
|------|-------------|---------------|--------------|----------|-------|
| 14:32 | VirusTotal | EEI 1.1.1 | Hash: abc123... | 45/70 detections | Screenshot: vt_001.png |
| 14:45 | Shodan | EEI 1.2.3 | IP: 203.0.113.10 | Port 80, 443 open | Apache 2.4.41 |
| 15:03 | crt.sh | EEI 1.1.2 | Domain: example.com | 15 certificates | Common CN pattern |
```

### Template 3: Infrastructure Map

```markdown
# Infrastructure Map

**Target**: [Threat Actor/Organization]
**Date**: [Date]

## Domains
| Domain | IP | First Seen | Last Seen | Status | Notes |
|--------|----|-----------| ----------|--------|-------|
| evil.com | 203.0.113.10 | 2024-01-15 | 2024-12-30 | Active | C2 server |

## IP Addresses
| IP | ASN | Hosting | Ports | Associated Domains |
|----|-----|---------|-------|-------------------|
| 203.0.113.10 | AS12345 | HostingCo | 80,443,8080 | evil.com, bad.net |

## Certificates
| SHA256 | Subject CN | Issuer | Valid From | Valid To | Associated Domains |
|--------|-----------|--------|------------|----------|-------------------|
| abc123... | evil.com | Let's Encrypt | 2024-06-01 | 2024-09-01 | evil.com, *.evil.com |

## Infrastructure Relationships
- [Describe connections between domains, IPs, certificates]
- [Note shared infrastructure patterns]
- [Identify clusters of related infrastructure]
```

### Template 4: Threat Actor Profile

```markdown
# Threat Actor Profile

**Threat Actor Name**: [Primary name]
**Aliases**: [Other names]
**Profile Date**: [Date]

## Attribution
**Confidence Level**: [High/Medium/Low]
**Attribution Sources**: [List of reports attributing activity]

## Overview
[Brief description of threat actor, motivation, sophistication]

## Capabilities
- [Technical capabilities]
- [Resource levels]
- [Sophistication assessment]

## TTPs (MITRE ATT&CK)
| Tactic | Technique | Technique ID | Notes |
|--------|-----------|--------------|-------|
| Initial Access | Spearphishing | T1566 | Targets executives |
| Execution | Command and Scripting | T1059 | Uses PowerShell |

## Infrastructure
[See Infrastructure Map template]

## Targeting
**Industries**: [Target industries]
**Geographies**: [Target countries/regions]
**Organization Types**: [Target org profiles]

## Activity Timeline
| Date | Campaign/Event | Description |
|------|----------------|-------------|
| 2024-01-15 | Campaign Alpha | Targeted finance sector |
| 2024-06-20 | Tool Release | Published new malware variant |

## IOCs
[List of indicators of compromise]

## Detection and Mitigation
[Detection rules, mitigation strategies]

## References
[List of threat intelligence reports and sources]
```

---

## Advanced Techniques

### Automation and Scripting

**Automate Repetitive Collection**:
- Use APIs for threat intel platforms (VirusTotal, AlienVault OTX)
- Script bulk WHOIS lookups
- Automate subdomain enumeration
- Build collection pipelines with Python

**Example Use Cases**:
- Daily checks for new IOCs in threat intel feeds
- Automated monitoring of breach databases for organization emails
- Continuous certificate transparency monitoring
- Scheduled passive DNS checks on known infrastructure

### Pivot Techniques

**Infrastructure Pivoting**:
1. Start with one IOC (domain, IP, hash)
2. Identify related artifacts (certificates, WHOIS, passive DNS)
3. Pivot to find additional related infrastructure
4. Repeat iteratively to map full infrastructure

**Identity Pivoting**:
1. Start with one identifier (email, username, phone)
2. Find associated accounts and profiles
3. Identify connections and relationships
4. Map identity network

### Data Fusion and Analysis

**Combining Multiple Sources**:
- Correlate findings from different collection phases
- Identify patterns across disparate data
- Use link analysis tools (Maltego, Gephi)
- Build timelines to understand sequences

**Confidence Scoring**:
- Assign confidence levels based on source reliability
- Require corroboration from multiple independent sources
- Document uncertainty and alternative hypotheses
- Use structured analytic techniques (ACH, etc.)

### Operational Security (OPSEC)

**Protecting Your Investigation**:
- Use VPNs or Tor for sensitive investigations
- Don't use personal accounts when investigating threat actors
- Be aware of tracking and fingerprinting
- Consider adversary monitoring of OSINT sources
- Document OPSEC measures taken

---

## Additional Resources

- **OSINT Collection Plan Framework**: [OSINT-COLLECTION-PLAN.md](OSINT-COLLECTION-PLAN.md) - Comprehensive intelligence requirements framework
- **Quick Start Guide**: [QUICK-START-GUIDE.md](QUICK-START-GUIDE.md) - Rapid investigation techniques
- **Tool Catalog**: [README.md](README.md) - Complete OSINT tool listing

---

**Last Updated**: December 30, 2024  
**Version**: 1.0  
**Maintainer**: @ltlfrappy21
# >>>>>>> main
