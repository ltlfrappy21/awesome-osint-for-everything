# OSINT Investigation Workflows

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
