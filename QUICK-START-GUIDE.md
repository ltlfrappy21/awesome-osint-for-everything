# OSINT Quick Start Guide

A rapid-reference guide for starting OSINT investigations using this repository.

## 🚀 Quick Investigation Templates

### 30-Minute Person Investigation

**Target:** [Name]

```
1. Google Search (5 min)
   - "Full Name" + location
   - "Full Name" + employer
   - "Full Name" + email

2. Social Media (10 min)
   - Facebook: facebook.com/search
   - LinkedIn: linkedin.com/search
   - Twitter: twitter.com/search
   - Instagram: instagram.com/[username]

3. Username Search (5 min)
   - WhatsMyName: https://whatsmyname.app
   - Search: [username] across platforms

4. Email/Phone (5 min)
   - Have I Been Pwned: https://haveibeenpwned.com
   - Dehashed: https://dehashed.com

5. Public Records (5 min)
   - TruePeopleSearch: https://truepeoplesearch.com
   - Fast People Search: Various tools in [People](#people) section
```

### 30-Minute Domain Investigation

**Target:** [domain.com]

```
1. Basic Info (5 min)
   - WHOIS: https://who.is
   - Historical WHOIS: WHOIS History tools

2. Infrastructure (10 min)
   - DNS Records: https://dnsdumpster.com
   - Subdomains: https://crt.sh
   - IP Info: https://securitytrails.com
   - SSL Certs: https://crt.sh

3. Technology (5 min)
   - Wappalyzer: https://wappalyzer.com
   - BuiltWith: https://builtwith.com

4. Content (5 min)
   - Wayback Machine: https://web.archive.org
   - Current site: Browse normally
   - Robots.txt: domain.com/robots.txt

5. Security (5 min)
   - VirusTotal: https://virustotal.com
   - URLScan: https://urlscan.io
```

### 30-Minute Company Investigation

**Target:** [Company Name]

```
1. Basic Info (5 min)
   - Google: "Company Name"
   - LinkedIn: Company page
   - Website: Official site

2. Business Records (10 min)
   - OpenCorporates: https://opencorporates.com
   - Business registrations
   - ICIJ Database: https://offshoreleaks.icij.org

3. Digital Presence (5 min)
   - Social media accounts
   - Review sites (Google, Yelp, etc.)
   - News mentions

4. People (5 min)
   - Key executives
   - LinkedIn employees
   - Contact information

5. Financial/Legal (5 min)
   - Court records
   - BBB complaints
   - SEC filings (if public)
```

## 🎯 Investigation Type Flowcharts

### Choose Your Investigation Path

```
START
  |
  ├─ Person? 
  |    └─> Use: Social Media + Username + Email + Public Records
  |
  ├─ Company?
  |    └─> Use: Business Records + Domain + Social + Financial
  |
  ├─ Domain/Website?
  |    └─> Use: WHOIS + DNS + Technology + Security + Content
  |
  ├─ Email Address?
  |    └─> Use: Breach DB + Email Tools + Reverse Search + Social
  |
  ├─ Phone Number?
  |    └─> Use: Reverse Lookup + Carrier Info + Breach DB
  |
  ├─ Username?
  |    └─> Use: Cross-platform Search + Social Media + Forums
  |
  └─ Location?
       └─> Use: Maps + Satellite + Webcams + GeoINT
```

## 🔍 Essential Tools by Category

### Must-Have Tools for Every Investigation

**Search & Discovery:**
- Google (with advanced operators)
- DuckDuckGo (privacy-focused)
- Yandex (Russian content)
- Bing (Microsoft index)

**Archiving & Preservation:**
- Wayback Machine: https://web.archive.org
- Archive.is: https://archive.is
- Screenshot tools

**Username Search:**
- WhatsMyName: https://whatsmyname.app
- Sherlock: (command-line tool)

**Email Intelligence:**
- Have I Been Pwned: https://haveibeenpwned.com
- Dehashed: https://dehashed.com
- Hunter.io: Email finder

**Domain/IP:**
- WHOIS: https://who.is
- SecurityTrails: https://securitytrails.com
- Shodan: https://shodan.io
- DNSDumpster: https://dnsdumpster.com

**Social Media:**
- Platform-specific search
- Social-searcher.com
- Google site: operator

**Documents & Files:**
- Google Dorks (filetype:)
- FOCA: Metadata extraction
- ExifTool: Image metadata

### Browser Extensions

**Chrome/Brave/Edge:**
- Wappalyzer (technology detection)
- OSINT Browser Extension
- DownThemAll (mass download)
- User-Agent Switcher

**Firefox:**
- All above plus
- Link Gopher (extract links)
- EXIF Viewer

## 📝 Quick Templates

### Evidence Documentation Template

```markdown
## Evidence Item

**ID:** E001
**Date Collected:** 2025-12-30
**Time:** 14:30 UTC
**Source:** [URL or platform]
**Archive:** [Link to archived version]
**Type:** [Screenshot/Document/Data]
**Relevance:** [High/Medium/Low]
**Description:** 
[What this evidence shows]

**Notes:**
- [Any relevant observations]
- [Follow-up needed]
```

### Daily Investigation Log

```markdown
# Investigation Log - [Date]

**Case:** [Case Name/Number]
**Investigator:** [Your ID]
**Date:** 2025-12-30

## Objectives Today
- [ ] Task 1
- [ ] Task 2
- [ ] Task 3

## Activities
**09:00-10:00** - [Activity description]
**10:00-11:00** - [Activity description]

## Key Findings
1. [Finding 1]
2. [Finding 2]

## Evidence Collected
- E001: [Description]
- E002: [Description]

## Tomorrow's Plan
- [ ] Follow-up on [item]
- [ ] Investigate [new lead]
```

## 🎓 Google Dork Cheat Sheet

### Finding Files
```
site:example.com filetype:pdf
site:example.com filetype:docx
site:example.com filetype:xlsx
site:example.com filetype:pptx
```

### Finding Directories
```
site:example.com intitle:"index of"
site:example.com inurl:admin
site:example.com inurl:backup
```

### Finding Login Pages
```
site:example.com inurl:login
site:example.com inurl:signin
site:example.com inurl:auth
```

### Finding People
```
site:linkedin.com "Company Name" "Job Title"
site:facebook.com "Person Name" "Location"
site:twitter.com "Person Name"
```

### Finding Exposed Data
```
site:example.com intext:"password"
site:example.com filetype:sql
site:example.com filetype:log
site:example.com intext:"confidential"
```

### Combining Operators
```
site:example.com (filetype:pdf OR filetype:docx) "confidential"
site:example.com inurl:admin -inurl:login
"John Smith" (site:linkedin.com OR site:facebook.com)
```

## ⚡ Speed Investigation Checklist

### Under 5 Minutes
- [ ] Google the target
- [ ] Check main social media (Facebook, LinkedIn, Twitter)
- [ ] WHOIS lookup (if domain)
- [ ] Email breach check

### Under 15 Minutes
- [ ] All of above, plus:
- [ ] Username search across platforms
- [ ] Reverse image search (if photo available)
- [ ] Public records quick search
- [ ] Domain/IP basic reconnaissance

### Under 30 Minutes
- [ ] All of above, plus:
- [ ] Deep social media analysis
- [ ] Historical data (Wayback Machine)
- [ ] Related entities identification
- [ ] Basic timeline construction

### Under 1 Hour
- [ ] All of above, plus:
- [ ] Comprehensive social media
- [ ] Advanced Google dorking
- [ ] Network/relationship mapping
- [ ] Multiple source verification

## 🛡️ Quick OPSEC Reminders

**Before Starting:**
- [ ] VPN connected
- [ ] Burner accounts ready
- [ ] Private/Incognito mode
- [ ] Tor (if needed)
- [ ] Separate browser profile

**During Investigation:**
- [ ] Don't use real identity
- [ ] Don't friend/follow targets
- [ ] Don't rapid-fire queries
- [ ] Clear cookies regularly
- [ ] Document everything

**After Investigation:**
- [ ] Clear browser data
- [ ] Archive all evidence
- [ ] Secure storage of findings
- [ ] Disconnect from target networks

## 🚨 Red Flags & Stop Signs

**Stop Immediately If:**
- You're asked for password/credentials
- Site requires payment for "public" records
- You're tempted to impersonate someone
- You're about to violate ToS
- You need to hack/exploit to proceed
- You're accessing illegal content
- Legal concerns arise

**Get Authorization Before:**
- Contacting the target directly
- Creating fake profiles
- Large-scale automated collection
- Accessing paid databases
- Sharing sensitive findings

## 📚 One-Page Reference

### Top 10 Starting Points

1. **Google** - Always start here
2. **Social Media** - Facebook, LinkedIn, Twitter, Instagram
3. **Username Search** - WhatsMyName, Sherlock
4. **Email Tools** - HIBP, Dehashed
5. **WHOIS** - Domain registration info
6. **Wayback Machine** - Historical snapshots
7. **Public Records** - TruePeopleSearch, CourtListener
8. **DNSDumpster** - DNS/subdomain recon
9. **VirusTotal** - Malware/URL analysis
10. **Shodan** - Internet device search

### Top 10 Google Operators

1. `site:` - Limit to specific site
2. `filetype:` - Find specific file types
3. `intitle:` - Words in page title
4. `inurl:` - Words in URL
5. `intext:` - Words in page content
6. `"exact phrase"` - Exact match
7. `OR` - Either term
8. `-term` - Exclude term
9. `*` - Wildcard
10. `..` - Number range

### Investigation Phases (Quick)

1. **Plan** (10% time) - Define what you need
2. **Collect** (40% time) - Gather information
3. **Process** (20% time) - Organize data
4. **Analyze** (20% time) - Find meaning
5. **Report** (10% time) - Present findings

## 🔗 Quick Links by Need

**Need to find a person?**
→ [People Section](README.md#people) | [Username Section](README.md#username) | [Social Media Section](README.md#social-media)

**Need to investigate a domain?**
→ [WHOIS Section](README.md#whois) | [Domain/IP/DNS Section](README.md#domain--ip--dns)

**Need to check for data breaches?**
→ [Breaches & Leaks Section](README.md#breaches-and-leaks)

**Need geolocation info?**
→ [Geo Section](README.md#geo) | [Maps Section](README.md#maps)

**Need threat intelligence?**
→ [Threat Intel Section](README.md#threat-intel) | [Malware Section](README.md#malware)

**Need to search social media?**
→ [Social Media Section](README.md#social-media) and platform-specific sections

## 💡 Pro Tips

1. **Always Archive** - Web content changes/disappears
2. **Multiple Sources** - Never trust single source
3. **Document Everything** - You'll forget details
4. **Stay Legal** - When in doubt, don't
5. **Pivot Often** - One finding leads to another
6. **Time Stamps** - Note when you found it
7. **Context Matters** - Understand what you're seeing
8. **Verify, Verify, Verify** - Confirm findings
9. **OPSEC Always** - Protect your identity
10. **Know When to Stop** - Respect boundaries

## 📖 Next Steps

After using this quick start guide, refer to:
- [Full OSINT Collection Plan](OSINT-COLLECTION-PLAN.md) for comprehensive methodology
- [Main README](README.md) for complete tool listings
- Individual tool sections for detailed capabilities

---

**Remember:** This is a quick reference for rapid investigations. For thorough, professional OSINT work, consult the full [OSINT Collection Plan](OSINT-COLLECTION-PLAN.md).

**Last Updated:** December 2025
