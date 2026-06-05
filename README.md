# Phishing Email Analysis Lab

---

## Project Overview

This project investigates a real-world phishing email sample
targeting PayPal users. The email was analyzed using 7 professional
cybersecurity tools to identify malicious indicators, attack
techniques, and threat infrastructure.

---

## What This Project Demonstrates

- Email header forensics (SPF, DKIM, DMARC analysis)
- IP address reputation investigation
- Malicious URL analysis and classification
- Sandbox-based behavior analysis (Any.run)
- Professional threat report writing
- Indicator of Compromise (IOC) extraction
- Real tool usage: VirusTotal, MXToolbox, AbuseIPDB

---

##  Repository Structure

```text
phishing-email-analysis-lab/
│
├── README.md
├── tools-used.md
│
├── emails/
│   └── phishing-sample-01.eml
│
├── analysis/
│   ├── sample-01-header-analysis.md
│   ├── url-analysis.md
│   └── sandbox-analysis.md
│
├── screenshots/
│   ├── 01-phishtank-sample.png
│   ├── 02-mxtoolbox-header.png
│   ├── 03-spf-dkim-dmarc-fail.png
│   ├── 04-virustotal-url-scan.png
│   ├── 05-urlscan-page-screenshot.png
│   ├── 06-urlscan-network-traffic.png
│   ├── 07-anyrun-sandbox.png
│   ├── 08-abuseipdb-ip-result.png
│   ├── 09-whois-domain-age.png
│   └── 10-project-folder.png
│
└── report/
└── final-report.md
```


---

## Phishing Sample Analyzed

| Attribute      | Detail                          |
|----------------|---------------------------------|
| Target Brand   | PayPal                          |
| Technique      | Domain Typosquatting            |
| Fake Domain    | paypa1-secure.com               |
| Real Domain    | paypal.com                      |
| Threat Level   | HIGH                            |
| Sender IP      | 185.220.101.47 (Tor Exit Node)  |
| IP Abuse Score | 100% — 6,561 reports            |
| URL Detection  | 13/91 security vendors          |
| Domain Status  | Suspended/Deleted               |

---

## Tools Used

| Tool       | Purpose                        |
|------------|--------------------------------|
| PhishTank  | Real phishing sample collection|
| MXToolbox  | Header and SPF/DKIM/DMARC check|
| VirusTotal | URL multi-engine scanning      |
| URLScan.io | URL behavior analysis          |
| AbuseIPDB  | IP reputation investigation    |
| Whois      | Domain registration check      |
| Any.run    | Interactive sandbox analysis   |

---

## Key Findings

### Malicious IP
185.220.101.47 — Tor Exit Node — Berlin Germany
AbuseIPDB: 100% abuse confidence — 6561 reports
### Malicious Domains
paypa1-secure.com
paypal-secure-login.xyz (suspended)
### Malicious URLs
hxxp://paypal-secure-login[.]xyz/verify?token=abc123
hxxp://185.220.101[.]47/track[.]php?id=victim123
### File Hash
MD5: ad951d13053484cadab5c5d496937aed
---

## Skills Demonstrated

- Email Header Forensics
- OSINT Investigation
- Threat Intelligence Analysis
- IOC Extraction and Documentation
- Sandbox Dynamic Analysis
- Professional Report Writing
- Social Engineering Recognition

---
