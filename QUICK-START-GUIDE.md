# OSINT Quick Start Guide

## Table of Contents

- [Introduction](#introduction)
- [Quick Investigation Framework](#quick-investigation-framework)
- [5-Step Rapid OSINT Process](#5-step-rapid-osint-process)
- [Scoping Investigations with PIRs and EEIs](#scoping-investigations-with-pirs-and-eeis)
- [Common Investigation Scenarios](#common-investigation-scenarios)
- [Essential Tools for Quick Start](#essential-tools-for-quick-start)
- [Documentation and Logging](#documentation-and-logging)
- [Next Steps](#next-steps)

---

## Introduction

This guide provides a rapid-start approach for conducting OSINT investigations. Whether you're investigating a security incident, performing reconnaissance, or assessing threats, this guide will help you quickly organize and execute effective OSINT collection.

**Who This Is For**:
- Security analysts responding to incidents
- Threat intelligence researchers starting new investigations
- Red team operators conducting reconnaissance
- Risk assessors evaluating new threats
- Anyone needing to quickly gather open-source intelligence

**Time to Start**: 15 minutes from reading to first collection

---

## Quick Investigation Framework

Every OSINT investigation, no matter how time-sensitive, should follow a basic structure:

```
1. DEFINE → What do I need to know? (Requirements)
2. IDENTIFY → Where can I find it? (Sources)
3. COLLECT → Gather the information (Execution)
4. ANALYZE → What does it mean? (Analysis)
5. DOCUMENT → Record findings and methods (Reporting)
```

**The Key Principle**: Start with clear requirements, even if you only spend 5 minutes defining them. Requirements-driven collection is always more efficient than exploratory collection.

---

## 5-Step Rapid OSINT Process

### Step 1: Define Your Priority Intelligence Requirements (5-10 minutes)

Start by answering: **"What specific questions do I need to answer?"**

Write down 3-5 **Priority Intelligence Requirements (PIRs)** - specific questions your investigation must answer.

**Good PIR Examples**:
- "What domains and IP addresses is threat actor group X currently using?"
- "Has employee email address Y appeared in any data breaches?"
- "What vulnerabilities exist in software product Z version A.B.C?"
- "Who is the registrant of domain example.com and what other domains do they own?"

**Poor PIR Examples** (too vague):
- "What can I find about Company X?" (No specific question)
- "Tell me about this threat actor" (No clear focus)
- "Is this suspicious?" (Needs more context)

**Template for Quick PIR Development**:

```
Investigation Target: [Person/Domain/IP/Organization/Threat Actor]
Investigation Purpose: [Incident Response/Threat Assessment/Due Diligence/Red Team]

PIR 1: [Specific question about infrastructure/identity/capability]
PIR 2: [Specific question about connections/relationships/attribution]
PIR 3: [Specific question about timeline/activity/intentions]
```

### Step 2: Identify Essential Elements of Information (5-10 minutes)

For each PIR, list the **Essential Elements of Information (EEIs)** - the specific data points you need to collect.

**Example Mapping**:

**PIR**: What domains and IP addresses is threat actor group X currently using?

**EEIs**:
- Domain names associated with threat actor X in the past 90 days
- IP addresses observed in recent campaigns attributed to X
- SSL/TLS certificate patterns used by X
- Registrant information for domains linked to X
- Passive DNS records for known X infrastructure

**Benefits**:
- Creates a clear collection checklist
- Prevents scope creep and wasted effort
- Helps identify which tools and sources to use
- Makes progress tracking straightforward

### Step 3: Map EEIs to OSINT Sources and Tools (5 minutes)

For each EEI, identify which categories of sources and tools can provide that information.

**EEI-to-Source Mapping Example**:

| EEI | Source Category | Specific Tools/Sources |
|-----|-----------------|------------------------|
| Domain names associated with threat actor | Threat Intelligence Platforms, Security Blogs | VirusTotal, AlienVault OTX, threat research blogs |
| IP addresses in recent campaigns | Network Intelligence, Passive DNS | Shodan, Censys, SecurityTrails, RiskIQ |
| SSL/TLS certificates | Certificate Transparency | crt.sh, Censys certificates, SSLMate |
| Registrant information | WHOIS, Domain Registration | WHOIS lookup tools, DomainTools, ViewDNS |

**Refer to Tool Categories in [README.md](README.md)**:
- [Domain / IP / DNS](#domain--ip--dns)
- [Threat Intel](#threat-intel)
- [Malware](#malware)
- [Source Codes](#source-codes)
- [Social Media](#social-media)

### Step 4: Execute Collection (Time-boxed)

**Time-Boxing**: Set a time limit for collection based on urgency:
- **Critical/Urgent**: 30-60 minutes initial collection
- **High Priority**: 2-4 hours initial collection
- **Standard**: 4-8 hours initial collection

**Collection Tips**:
- Start with the highest-priority PIR
- Collect systematically, checking off EEIs as you go
- Document sources and timestamps for everything
- Take screenshots of key findings
- Save raw data for later analysis

**Avoid Common Pitfalls**:
- Don't get sidetracked by interesting but irrelevant information
- Don't spend excessive time on a single source if it's not productive
- Don't forget to document as you collect (memory is unreliable)

### Step 5: Rapid Analysis and Documentation (30-60 minutes)

**Answer Your PIRs**:
- For each PIR, summarize what you learned
- Note confidence level (High/Medium/Low) based on source reliability
- Identify gaps where PIRs remain unanswered

**Document**:
- Which EEIs were satisfied and which remain gaps
- Sources used and their reliability
- Key findings and their supporting evidence
- Next steps and follow-on PIRs

**Basic Report Template**:

```markdown
## Investigation Summary
**Date**: [Date]
**Investigator**: [Name/Handle]
**Target**: [What was investigated]
**Purpose**: [Why investigation was conducted]

## Priority Intelligence Requirements (PIRs) and Answers

### PIR 1: [Question]
**Answer**: [What you found]
**Confidence**: [High/Medium/Low]
**Sources**: [Tools and sources used]
**Evidence**: [Key supporting data points]

### PIR 2: [Question]
[Repeat structure]

## Intelligence Gaps
- [PIRs not fully answered]
- [Information that could not be obtained]

## Follow-on Requirements
- [New PIRs generated from findings]
- [Areas requiring deeper investigation]

## Collection Log
| Time | Source | EEI Addressed | Findings |
|------|--------|---------------|----------|
| [Time] | [Source/Tool] | [EEI ID] | [Brief note] |
```

---

## Scoping Investigations with PIRs and EEIs

### Why Requirements Matter for Quick Investigations

Even under time pressure, spending 10 minutes defining PIRs and EEIs will:
1. **Save time** by preventing unfocused collection
2. **Improve results** by ensuring you collect what actually matters
3. **Enable prioritization** when time runs out
4. **Facilitate handoffs** if someone else needs to continue
5. **Support reporting** with clear structure

### Quick PIR Development by Investigation Type

#### Threat Actor Investigation

**Quick PIRs**:
1. What is the threat actor's current infrastructure? (domains, IPs, certificates)
2. What TTPs is the threat actor currently using? (tools, techniques, procedures)
3. Who or what is the threat actor targeting? (industries, geographies, organizations)
4. What is the threat actor's recent activity timeline? (campaigns, attacks, announcements)

#### Domain/IP Investigation

**Quick PIRs**:
1. Who owns this domain/IP and what other assets do they control?
2. What services and technologies are running on this IP/domain?
3. What is the history and reputation of this domain/IP?
4. What connections exist between this asset and known threat activity?

#### Identity Investigation (Person/Organization)

**Quick PIRs**:
1. What online accounts and profiles are associated with this identity?
2. What data breaches or leaks involve this identity?
3. What public information is available about this identity's activities?
4. What connections exist between this identity and other entities?

#### Vulnerability Investigation

**Quick PIRs**:
1. What technical details are publicly available about this vulnerability?
2. Are there public exploits or proof-of-concepts available?
3. What threat actors are known to exploit this vulnerability?
4. What mitigations and detections are available?

### EEI Quick Reference by PIR Type

| PIR Category | Common EEIs | OSINT Sources |
|--------------|-------------|---------------|
| **Infrastructure** | Domains, IPs, certificates, hosting providers, ASNs | WHOIS, passive DNS, Shodan, Censys, crt.sh |
| **Identity** | Email addresses, usernames, social profiles, breach data | Breach databases, social media, username search tools |
| **Malware/Tools** | File hashes, signatures, code repositories, distribution sites | VirusTotal, GitHub, malware sandboxes |
| **Attribution** | Aliases, patterns, language, timezone indicators, TTPs | Threat intel platforms, forums, social media |
| **Timeline** | First seen dates, last seen dates, activity patterns | Historical archives, passive DNS, certificate logs |

---

## Common Investigation Scenarios

### Scenario 1: Suspicious Email Investigation (15-30 minutes)

**Situation**: You received a suspicious email and need to determine if it's a threat.

**Quick PIRs**:
1. Is the sender email address or domain known to be malicious?
2. Are there indicators of phishing or malware in the email content?
3. Has this sender/domain been reported for abuse?

**Collection Checklist**:
- [ ] Check sender email address in breach databases (HaveIBeenPwned, DeHashed)
- [ ] WHOIS lookup on sender domain
- [ ] Check domain reputation (VirusTotal, URLVoid)
- [ ] Analyze any URLs in email (URLScan.io, VirusTotal)
- [ ] Check any attachments (VirusTotal, Hybrid Analysis)
- [ ] Search for sender address/domain in threat intel feeds (AlienVault OTX)

**Tools**: [Email](#email), [Domain / IP / DNS](#domain--ip--dns), [Threat Intel](#threat-intel) sections in main README

### Scenario 2: Compromised Credentials Check (10-20 minutes)

**Situation**: You need to check if employee credentials have been compromised.

**Quick PIRs**:
1. Have our employee email addresses appeared in any data breaches?
2. Are any employee credentials being sold or shared in underground forums?
3. What information about our organization is available in leak databases?

**Collection Checklist**:
- [ ] Check email addresses in HaveIBeenPwned
- [ ] Search DeHashed for domain-associated credentials
- [ ] Check Intelligence X for organization mentions
- [ ] Search LeakRadar for recent credential exposures
- [ ] Check GitHub for accidentally committed credentials (.env files, config files)

**Tools**: [Breaches & Leaks](#breaches-and-leaks), [Source Codes](#source-codes) sections in main README

### Scenario 3: New Threat Actor Research (1-2 hours)

**Situation**: A new threat actor has been identified and you need to build an initial profile.

**Quick PIRs**:
1. What infrastructure is associated with this threat actor?
2. What are the threat actor's TTPs and tools?
3. What industries or targets is this threat actor focused on?
4. What is the timeline of this threat actor's known activity?

**Collection Checklist**:
- [ ] Search threat intel platforms (AlienVault OTX, MISP)
- [ ] Review security vendor blog posts and reports
- [ ] Search for mentions in Twitter/X security community
- [ ] Check for related malware samples (VirusTotal, Any.Run)
- [ ] Identify IOCs (domains, IPs, hashes) from reports
- [ ] Map TTPs to MITRE ATT&CK framework
- [ ] Search for actor aliases and naming variations

**Tools**: [Threat Intel](#threat-intel), [Malware](#malware), [Social Media](#social-media) sections in main README

### Scenario 4: Third-Party Vendor Security Assessment (2-4 hours)

**Situation**: You need to assess the security posture of a third-party vendor.

**Quick PIRs**:
1. What security incidents or breaches has this vendor experienced?
2. What is the vendor's external attack surface? (domains, IPs, exposed services)
3. Are there any public vulnerabilities or misconfigurations in vendor systems?
4. What is the vendor's reputation in the security community?

**Collection Checklist**:
- [ ] Search for vendor in breach databases and news
- [ ] Enumerate vendor domains and subdomains
- [ ] Scan vendor external IPs (Shodan, Censys)
- [ ] Check for exposed services and data (Shodan, BinaryEdge)
- [ ] Search for vendor employee credentials in leaks
- [ ] Review vendor security advisories and CVEs
- [ ] Check social media for security discussions about vendor

**Tools**: [Domain / IP / DNS](#domain--ip--dns), [Breaches & Leaks](#breaches-and-leaks), [IoT](#iot) sections in main README

---

## Essential Tools for Quick Start

### Must-Have Tools by Category

#### Infrastructure Investigation
- **WHOIS Lookup**: [ViewDNS.info WHOIS](https://viewdns.info/whois/)
- **Passive DNS**: [SecurityTrails](https://securitytrails.com/)
- **IP/Port Scanning**: [Shodan](https://www.shodan.io/)
- **Certificate Transparency**: [crt.sh](https://crt.sh/)

#### Identity Investigation
- **Breach Data**: [HaveIBeenPwned](https://haveibeenpwned.com/), [DeHashed](https://www.dehashed.com/)
- **Username Search**: [WhatsMyName](https://whatsmyname.app/)
- **Email Search**: [Hunter.io](https://hunter.io/), [Prospeo](https://prospeo.io/)

#### Threat Intelligence
- **Multi-Source Intel**: [VirusTotal](https://www.virustotal.com/)
- **Threat Feed**: [AlienVault OTX](https://otx.alienvault.com/)
- **Malware Analysis**: [Hybrid Analysis](https://hybrid-analysis.com/), [Any.Run](https://any.run/)

#### General Purpose
- **Google Dorking**: Advanced Google searches
- **Archive Search**: [Wayback Machine](https://archive.org/web/)
- **Metadata Analysis**: [ExifTool](https://exiftool.org/)

**Full Tool Catalog**: See [README.md](README.md) for comprehensive tool listings

### Tool Selection Tips

1. **Start Broad, Then Narrow**: Use aggregators (VirusTotal, OTX) first, then specialized tools
2. **Free vs. Paid**: Most quick investigations can use free tiers
3. **API Access**: Set up API keys for frequent tools to speed up collection
4. **Browser Extensions**: Install helpful extensions (Shodan, BuiltWith) for rapid lookups
5. **Command Line**: Learn CLI tools (curl, whois, dig) for automation

---

## Documentation and Logging

### Why Document During Collection

- **Memory is unreliable**: You will forget details within minutes
- **Legal/Compliance**: Investigations may need to be defensible
- **Collaboration**: Others may need to continue your work
- **Learning**: Improve your process over time
- **Reporting**: Easier to write reports with good notes

### Minimum Documentation Standard

For every investigation, document:
1. **Date and time** investigation started
2. **Purpose** of the investigation (PIRs)
3. **Sources used** and timestamps
4. **Key findings** with supporting evidence
5. **Intelligence gaps** and unanswered questions

### Quick Logging Template

Create a simple text file or note for each investigation:

```
INVESTIGATION LOG
=================
Date: YYYY-MM-DD HH:MM
Investigator: [Your Name]
Target: [What you're investigating]

PIRs:
1. [Question 1]
2. [Question 2]
3. [Question 3]

COLLECTION LOG:
---------------
[HH:MM] - Checked [Source] - Found [Brief finding]
[HH:MM] - Searched [Tool] for [Query] - Result: [Summary]
[HH:MM] - Screenshot saved: [Filename]

KEY FINDINGS:
-------------
- [Finding 1 with source]
- [Finding 2 with source]

GAPS:
-----
- [What couldn't be found]

NEXT STEPS:
-----------
- [Follow-on actions needed]
```

### Screenshot and Evidence Management

- **Take screenshots** of key findings (web pages change or disappear)
- **Save raw data** (JSON, CSV exports) when possible
- **Organize by investigation** (create a folder per investigation)
- **Name files descriptively**: `20241230_shodan_targetIP_screenshot.png`
- **Don't rely on browser history**: Export bookmarks or save URLs to text file

---

## Next Steps

### Expanding Your Investigation

After completing quick OSINT collection:

1. **Review and Prioritize Gaps**: What unanswered PIRs are most critical?
2. **Develop Follow-on PIRs**: What new questions emerged from findings?
3. **Deeper Analysis**: Move from collection to analysis of patterns and connections
4. **Report Findings**: Share intelligence with stakeholders in appropriate format

### Deepening Your Skills

- **Read Full Collection Plan**: [OSINT-COLLECTION-PLAN.md](OSINT-COLLECTION-PLAN.md) for comprehensive requirements framework
- **Study Workflows**: [INVESTIGATION-WORKFLOWS.md](INVESTIGATION-WORKFLOWS.md) for detailed investigation methodologies
- **Explore Tools**: Browse [README.md](README.md) to discover tools for specific use cases
- **Practice**: The more investigations you conduct, the faster and better you'll become

### Advanced Topics

Once comfortable with quick investigations, explore:
- **Automation**: Scripting common collection tasks
- **API Integration**: Building automated collection pipelines
- **Data Analysis**: Using tools like Maltego or Python for link analysis
- **Threat Intelligence Platforms**: Integrating findings into TIP systems
- **Advanced Workflows**: Complex multi-stage investigations

---

## Additional Resources

- **OSINT Collection Plan Framework**: [OSINT-COLLECTION-PLAN.md](OSINT-COLLECTION-PLAN.md)
- **Detailed Investigation Workflows**: [INVESTIGATION-WORKFLOWS.md](INVESTIGATION-WORKFLOWS.md)
- **Comprehensive Tool Catalog**: [README.md](README.md)

---

## Tips for Success

**Do**:
✅ Define PIRs before collecting  
✅ Document as you work  
✅ Use multiple sources to corroborate  
✅ Stay focused on requirements  
✅ Set time limits to prevent scope creep  

**Don't**:
❌ Start collecting without requirements  
❌ Trust a single source without corroboration  
❌ Get distracted by interesting but irrelevant information  
❌ Forget to document sources and timestamps  
❌ Continue indefinitely without time-boxing  

---

**Last Updated**: December 30, 2024  
**Version**: 1.0  
**Maintainer**: @ltlfrappy21
