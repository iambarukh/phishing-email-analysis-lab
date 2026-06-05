# Sandbox Analysis Report — Sample 01 (PayPal Phishing)

## Tool Used
**Any.run** (app.any.run) — Interactive Online Sandbox

**Analysis Date:** June 5, 2026

**File Analyzed:** phishing-sample-01.eml

**MD5:** ad951d13053484cadab5c5d496937aed

---

## Analysis Environment

| Setting        | Value                        |
|----------------|------------------------------|
| OS             | Windows 10 Professional 64bit|
| Start Time     | 05.06.2026, 13:05            |
| Total Time     | 69 seconds                   |
| Platform       | Any.run Interactive Sandbox  |

---

## What Happened When Email Opened

### Process Tree
OUTLOOK.EXE (PID: 8004)
└── ai.exe (PID: 8704)
└── Child process spawned
### Explanation:
- Sandbox automatically opened email in **Microsoft Outlook**
- Outlook launched **ai.exe** as child process
- This shows email triggered additional execution

---

## Network Activity Detected

### Summary
| Type            | Count  |
|-----------------|--------|
| HTTP Requests   | 27     |
| Connections     | 20     |
| DNS Requests    | 20     |
| Network Threats | 1      |

### Network Threat Detected
| Field      | Value                                    |
|------------|------------------------------------------|
| Class      | Unknown Traffic                          |
| Process    | svchost.exe (PID: 2320)                  |
| Alert      | ET USER_AGENTS Microsoft Dr Watson       |
| Time       | 4453 ms after execution                  |
| Severity   | SUSPICIOUS                               |

### Key HTTP Connections Made
| Process       | URL                              | Status |
|---------------|----------------------------------|--------|
| OUTLOOK.EXE   | officeclient.microsoft.com       | 200 OK |
| OUTLOOK.EXE   | ecs.office.com                   | 200 OK |
| svchost.exe   | login.live.com/RST2.srf          | 200 OK |
| svchost.exe   | login.live.com/deviceaddcredential| 400   |
| OUTLOOK.EXE   | self.events.data.microsoft.com   | 200 OK |

---

## Indicators of Compromise (IOCs)

### File IOC
File: phishing-sample-01.eml
MD5:  ad951d13053484cadab5c5d496937aed
### Network IOCs (Defanged)
hxxp://paypal-secure-login[.]xyz/verify?token=abc123
hxxp://185.220.101[.]47/track[.]php?id=victim123
### IP IOC
185.220.101.47 — Tor Exit Node — Berlin, Germany
AbuseIPDB Score: 100% malicious
Total Reports: 6,561
---

## Sandbox Findings Summary

| Category        | Finding                          | Severity  |
|-----------------|----------------------------------|-----------|
| Email Opened    | Outlook auto-executed email      | INFO      |
| Child Process   | ai.exe spawned by Outlook        | SUSPICIOUS|
| Network Threat  | ET USER_AGENTS alert triggered   | SUSPICIOUS|
| HTTP Activity   | 27 requests made                 | SUSPICIOUS|
| Credential URL  | login.live.com contacted         | HIGH      |
| Tracking Pixel  | 185.220.101.47 contact attempted | HIGH      |

---

## Verdict

**MALICIOUS EMAIL — CONFIRMED**

The sandbox analysis confirms:
- Email automatically executes when opened
- Spawns child processes (ai.exe)
- Makes 27 network connections
- Triggers network threat detection rule
- Attempts to contact malicious tracking server
- Contacts credential-related endpoints
