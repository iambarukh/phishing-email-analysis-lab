# Tools Used — Phishing Email Analysis Lab

## All Tools Used in This Project

| Tool       | Website              | Purpose                        | Used For         |
|------------|----------------------|--------------------------------|------------------|
| PhishTank  | phishtank.org        | Phishing URL database          | Sample collection|
| MXToolbox  | mxtoolbox.com        | Email header + SPF/DKIM/DMARC  | Header analysis  |
| VirusTotal | virustotal.com       | Multi-engine URL/IP scanner    | URL analysis     |
| URLScan.io | urlscan.io           | URL behavior analysis          | URL analysis     |
| AbuseIPDB  | abuseipdb.com        | IP reputation database         | IP investigation |
| Whois      | whois command | Domain registration info       | Domain age check |
| Any.run    | app.any.run          | Interactive sandbox            | Behavior analysis|

---

## How Each Tool Was Used

### 1. PhishTank
- Visited phishtank.org
- Searched for real phishing submissions
- Collected sample phishing URL for analysis
- Verified URL was active and reported

### 2. MXToolbox
- Pasted email headers from phishing-sample-01.eml
- Analyzed SPF, DKIM, DMARC authentication
- Result: IP 185.220.101.47 found on blacklist
- Confirmed email authentication completely failed

### 3. VirusTotal
- Scanned URL: paypal-secure-login.xyz
- Result: 10/91 security vendors flagged malicious
- Vendors: BitDefender, Kaspersky, ESET, Sophos etc.
- Verdict: PHISHING confirmed

### 4. URLScan.io
- Scanned domain: paypal-secure-login.xyz
- Result: 13/91 vendors flagged (more than VirusTotal)
- Domain scan showed increasing detection over time
- Confirmed active phishing campaign

### 5. AbuseIPDB
- Investigated IP: 185.220.101.47
- Result: 100% abuse confidence score
- Total reports: 6,561 from 593 sources
- Type: Tor Exit Node — Berlin, Germany
- Still actively reported (10 hours before analysis)

### 6. Whois 
- whois paypal-secure-login.xyz
- Result: DOMAIN NOT FOUND
- Domain was suspended/deleted due to malicious activity
- Confirms security vendors took action

### 7. Any.run
- Uploaded phishing-sample-01.eml directly
- Sandbox opened email in Windows 10 environment
- Detected: 1 Network Threat (ET USER_AGENTS alert)
- Observed: 27 HTTP requests, 20 DNS requests
- Found: Child process ai.exe spawned
- MD5: ad951d13053484cadab5c5d496937aed

---

## Key Findings Per Tool

| Tool       | Key Finding                          | Severity  |
|------------|--------------------------------------|-----------|
| PhishTank  | Real phishing URL collected          | INFO      |
| MXToolbox  | IP blacklisted, SPF/DKIM/DMARC fail  | HIGH      |
| VirusTotal | 10/91 malicious detections           | HIGH      |
| URLScan    | 13/91 malicious detections           | HIGH      |
| AbuseIPDB  | 100% abuse — 6561 reports            | CRITICAL  |
| Whois      | Domain suspended/deleted             | HIGH      |
| Any.run    | Network threat + child process       | HIGH      |
