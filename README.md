Incident Reports
 
![Blue Team Labs Online](https://img.shields.io/badge/BTLO-10%2F10-brightgreen?style=flat)
![LetsDefend](https://img.shields.io/badge/LetsDefend-Sysmon_Analysis-blue?style=flat)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK-red?style=flat)
![Phishing](https://img.shields.io/badge/Phishing-Analysis-yellow?style=flat)
 
Real investigation write-ups from my 180-day SOC analyst roadmap. Each report documents an actual challenge or investigation — the methodology, findings, IOCs, and conclusions. Written for different audiences to practice professional communication.
 
---
 
## Reports
 
### Phishing Email Investigation
**Date:** 2026-06-08
**Source:** Blue Team Labs Online — Phishing Analysis challenge (10/10)
**Severity:** Medium
**Status:** Closed
 
**Summary:** A user received a phishing email disguised as a delivery failure notification. The malicious URL was hidden inside a nested .eml attachment — a deliberate evasion technique to bypass email scanners that only inspect the top-level message. The destination page was hosted on Blogspot to abuse Google's trusted domain reputation.
 
**Files:**
- `phishing-analysis/day24-btlo-phishing.md` — full investigation notes and methodology
- `phishing-analysis/day24-technical-report.md` — technical report (SOC manager audience)
- `phishing-analysis/day24-executive-summary.md` — executive summary (CISO audience)
- `phishing-analysis/day24-user-email.md` — plain English communication (affected user)
**Key IOCs:**
| Type | Value |
|------|-------|
| Subject | `Undeliverable: Website contact form submission` |
| Sending infrastructure | `c5s2-1e-syd.hosting-services.net.au` |
| Attachment | `Website contact form submission.eml` |
| Malicious URL | `https://35000usdperwwekpodf.blogspot.sg?p=3D9swg` |
| Hosting platform | Blogspot (Google) |
 
**What made this interesting:** The nested .eml structure — malicious content inside an attachment inside an email — is a scanner evasion technique I hadn't seen before doing this investigation. Most automated tools only parse the top-level message.
 
---
 