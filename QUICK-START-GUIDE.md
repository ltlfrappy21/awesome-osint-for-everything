# OSINT Quick Start Guide

## Introduction

This guide provides a rapid entry point for conducting OSINT (Open-Source Intelligence) investigations. Whether you're a security researcher, investigator, or analyst, these quick-start techniques will help you begin gathering intelligence efficiently.

## Anchor Your Investigation: PIRs and EEIs

Before diving into tools and techniques, take a moment to define what you're looking for. Even in quick, tactical investigations, clarity of purpose dramatically improves efficiency and results.

### Define Your Priority Intelligence Requirement (PIR)

Ask yourself: **What specific question am I trying to answer?**

A well-formed PIR is:
- **Specific**: Clear and unambiguous
- **Measurable**: You'll know when you've answered it
- **Actionable**: The answer informs a decision or action
- **Time-bound**: Has a relevant timeframe (when appropriate)

**Examples of good PIRs for quick investigations:**
- "Has user @example disclosed personal information on social media in the past 6 months?"
- "What email addresses are associated with the domain example.com?"
- "Has the IP address 192.0.2.1 been reported in threat intelligence feeds in the past 30 days?"
- "What technologies is acme-corp.com using for their web infrastructure?"

### Identify Your Essential Elements of Information (EEIs)

Once you have your PIR, list the specific data points you need:

**Example - For PIR: "What technologies is acme-corp.com using?"**

Your EEIs might include:
- Web server type and version
- SSL/TLS certificate details
- DNS records (A, MX, TXT, SPF, DMARC)
- HTTP headers revealing frameworks
- JavaScript libraries loaded on pages
- Third-party services integrated

Having clear EEIs helps you:
- Select the right tools immediately
- Stay focused during investigation
- Know when you've gathered enough information
- Organize findings systematically

**Quick Tip**: Write down your PIR and 3-5 EEIs before opening any tools. This 30-second exercise will save you hours of unfocused searching.

---

## Essential First Steps

### 1. Search Engines
Start with targeted search engine queries:

**Google Dorking Examples:**
```
site:example.com filetype:pdf
intitle:"index of" site:example.com
inurl:admin site:example.com
"@example.com" site:linkedin.com
```

**Tools:**
- [Google](https://www.google.com)
- [DuckDuckGo](https://duckduckgo.com)
- [Bing](https://www.bing.com)

### 2. Domain and IP Investigation
Quickly gather infrastructure information:

**Key Actions:**
- WHOIS lookup for registration details
- DNS records for mail servers, subdomains
- Certificate transparency logs for associated domains
- Reverse IP lookup for other sites on same server

**Tools from Awesome OSINT:**
- Refer to [Domain / IP / DNS section](README.md#domain--ip--dns) in README
- Refer to [Whois section](README.md#whois) in README

### 3. Social Media Reconnaissance
Search for presence across platforms:

**Quick Checks:**
- Username search across multiple platforms
- Profile information and connections
- Posted content and timeline
- Associated accounts and emails

**Tools from Awesome OSINT:**
- Refer to [Username section](README.md#username) in README
- Refer to [Social Media section](README.md#social-media) in README

### 4. Email Investigation
Gather intelligence about email addresses:

**Key Actions:**
- Check for data breach exposure
- Find associated accounts and services
- Verify email deliverability
- Identify email patterns in organization

**Tools from Awesome OSINT:**
- Refer to [Email section](README.md#email) in README
- Refer to [Breaches and Leaks section](README.md#breaches-and-leaks) in README

### 5. People Search
Find information about individuals:

**Quick Checks:**
- Public records and background
- Professional profiles (LinkedIn)
- Social media presence
- Contact information

**Tools from Awesome OSINT:**
- Refer to [People section](README.md#people) in README

## Quick Investigation Workflows

### Workflow 1: Unknown Email Address
**PIR**: Who owns this email address and what can I learn about them?

**EEIs**: Name, organization, social media profiles, breach history, other associated emails

**Steps:**
1. Check breach databases (HaveIBeenPwned, Dehashed)
2. Search email in Google with quotes: "email@example.com"
3. Check social media platforms
4. Reverse email lookup tools
5. Check username portion across platforms

**Time estimate**: 15-30 minutes

### Workflow 2: Company/Domain Investigation
**PIR**: What is the digital footprint of this organization?

**EEIs**: Infrastructure details, employee information, technology stack, public documents, social media presence

**Steps:**
1. WHOIS and DNS reconnaissance
2. Certificate transparency logs
3. Google dorking for indexed files and subdomains
4. Technology profiling (BuiltWith, Wappalyzer)
5. Employee identification via LinkedIn
6. News and public records search

**Time estimate**: 30-60 minutes

### Workflow 3: Username Investigation
**PIR**: Where does this username appear online?

**EEIs**: Associated platforms, profile information, posted content, connections

**Steps:**
1. Use username search tools (WhatsMyName, Namechk)
2. Search username in quotes on Google
3. Check major social platforms manually
4. Look for associated emails or usernames
5. Timeline analysis of account activity

**Time estimate**: 20-40 minutes

### Workflow 4: IP Address Investigation
**PIR**: What can I learn about this IP address?

**EEIs**: Ownership, geolocation, hosting provider, associated domains, threat reputation

**Steps:**
1. WHOIS lookup
2. Reverse DNS
3. Geolocation services
4. Threat intelligence feeds
5. Reverse IP lookup for hosted domains
6. Port scanning (if authorized)

**Time estimate**: 15-30 minutes

## Best Practices for Quick Investigations

### Documentation
- **Take notes immediately**: Don't rely on memory
- **Screenshot key findings**: Evidence may disappear
- **Record timestamps**: When was information observed
- **Document sources**: Where did each piece of information come from
- **Track your EEIs**: Check off each one as you find it

### Privacy and Ethics
- **Stay within legal bounds**: Respect ToS and laws
- **Don't interact**: Passive collection only
- **Use VPNs appropriately**: Protect your identity when necessary
- **Consider operational security**: Don't reveal your investigation

### Efficiency Tips
- **Batch similar tasks**: Do all Google searches together, all social media checks together
- **Use browser profiles**: Keep investigation browsers separate
- **Leverage automation**: Use APIs and scripts for repetitive tasks
- **Know when to stop**: Your PIR tells you when you're done
- **Review your EEI checklist**: Ensure you've covered all essential elements

### Common Pitfalls to Avoid
- **Scope creep**: Staying focused on your PIR prevents rabbit holes
- **Unverified information**: Corroborate findings across multiple sources
- **Outdated data**: Check timestamps and recency
- **Missing context**: Understand the bigger picture
- **Over-reliance on single tools**: Cross-validate with multiple methods

## Tools Quick Reference

Instead of listing all tools here, this guide points you to the comprehensive tool listings in README.md. Use these categories based on your investigation needs:

- **Username searches**: [Username section](README.md#username)
- **Email investigations**: [Email section](README.md#email)
- **Domain/IP research**: [Domain / IP / DNS section](README.md#domain--ip--dns)
- **Social media**: [Social Media section](README.md#social-media)
- **Breaches**: [Breaches and Leaks section](README.md#breaches-and-leaks)
- **People search**: [People section](README.md#people)
- **Phone numbers**: [Phone section](README.md#phone)
- **Images**: [Images and Audio section](README.md#images-and-audio)
- **Threat intelligence**: [Threat Intel section](README.md#threat-intel)

For structured investigations with more complexity, refer to:
- **[OSINT-COLLECTION-PLAN.md](OSINT-COLLECTION-PLAN.md)** - Comprehensive intelligence collection framework
- **[INVESTIGATION-WORKFLOWS.md](INVESTIGATION-WORKFLOWS.md)** - Detailed investigation workflows and decision trees

## Advanced Quick Techniques

### Passive DNS
- Query historical DNS records
- Identify infrastructure changes over time
- Find previously associated domains

### Certificate Transparency
- Search for SSL certificates by domain
- Find subdomains and related infrastructure
- Identify certificate reuse patterns

### GitHub Reconnaissance
- Search for organization repositories
- Find exposed credentials or API keys
- Identify developer accounts and activity
- Check commit history for sensitive data

### Image Reverse Search
- Find where images appear online
- Identify original sources
- Discover related images and profiles

### Metadata Analysis
- Extract EXIF data from images
- Analyze document metadata
- Identify creation tools and timestamps

## Emergency Quick Checks

When time is extremely limited, these are the highest-value quick checks:

**For People (5 minutes):**
1. Google search with quotes
2. HaveIBeenPwned
3. LinkedIn quick search

**For Domains (5 minutes):**
1. WHOIS lookup
2. VirusTotal domain check
3. Certificate transparency search

**For IPs (5 minutes):**
1. WHOIS lookup
2. AbuseIPDB check
3. Reverse DNS

**For Usernames (5 minutes):**
1. WhatsMyName or Sherlock tool
2. Google search with quotes
3. Twitter/X search

## Next Steps

Once you've completed your quick investigation:

1. **Organize findings**: Structure notes and screenshots
2. **Verify information**: Cross-check critical findings
3. **Fill intelligence gaps**: Identify unanswered EEIs
4. **Expand if needed**: Use INVESTIGATION-WORKFLOWS.md for deeper dives
5. **Report results**: Share findings with stakeholders
6. **Archive properly**: Store evidence securely

For more structured, comprehensive investigations, proceed to:
- **[INVESTIGATION-WORKFLOWS.md](INVESTIGATION-WORKFLOWS.md)** for detailed methodologies
- **[OSINT-COLLECTION-PLAN.md](OSINT-COLLECTION-PLAN.md)** for formal collection planning

---

**Document Version**: 1.0  
**Last Updated**: 2025-12-30  
**Maintainer**: @ltlfrappy21

## Contributing

Found a useful quick technique or tool? Contributions are welcome! Please ensure additions maintain the "quick start" focus of this guide.
