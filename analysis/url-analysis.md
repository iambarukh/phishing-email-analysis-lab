# URL Analysis Report — Sample 01 (PayPal Phishing)

## Malicious URL Found in Email
http://paypal-secure-login.xyz/verify?token=abc123
---

## VirusTotal Scan Results

**Tool:** VirusTotal (virustotal.com)
**Scan Date:** June 5, 2026

| Metric          | Result                        |
|-----------------|-------------------------------|
| Detection Rate  | 10/91 security vendors        |
| Verdict         | MALICIOUS / PHISHING          |

### Vendors That Flagged:
| Vendor          | Verdict   |
|-----------------|-----------|
| BitDefender     | Phishing  |
| Kaspersky       | Phishing  |
| ESET            | Phishing  |
| Fortinet        | Phishing  |
| Sophos          | Phishing  |
| G-Data          | Phishing  |
| Lionic          | Phishing  |
| Webroot         | Malicious |
| ADMINUSLabs     | Malicious |
| Chong Lua Dao   | Malicious |

---

## URLScan.io Results

**Tool:** URLScan.io (urlscan.io)
**Scan Date:** June 5, 2026

| Metric          | Result                        |
|-----------------|-------------------------------|
| Detection Rate  | 13/91 security vendors        |
| Verdict         | MALICIOUS / PHISHING          |

### Additional Vendors Flagged:
| Vendor          | Verdict   |
|-----------------|-----------|
| alphaMountain   | Phishing  |
| CyRadar         | Phishing  |
| VIPRE           | Phishing  |

---

## Domain Investigation

**Domain:** paypal-secure-login.xyz

| Check           | Result                                    |
|-----------------|-------------------------------------------|
| Whois Status    | DOMAIN NOT FOUND — Deleted/Suspended      |
| Reason          | Flagged by multiple security vendors      |
| Real PayPal     | paypal.com (registered since 1999)        |
| Fake Domain     | paypal-secure-login.xyz (deleted)         |

---

## Tracking Pixel Found

**URL:** `http://185.220.101.47/track.php?id=victim123`

| Detail    | Value                                      |
|-----------|--------------------------------------------|
| Purpose   | 1x1 invisible pixel — tracks email opens  |
| Risk       | Reveals victim IP, location, email client |
| IP        | 185.220.101.47 (Tor exit node — Germany)  |

### How Tracking Pixel Works:
1. Victim opens email
2. Invisible image loads from attacker server
3. Attacker records: victim IP, location, device, email client
4. Attacker knows email was opened

---

## Red Flags Summary

1. Domain typosquatting — `paypal-secure-login.xyz`
2. Flagged by 13 security vendors
3. Domain completely deleted/suspended
4. Tracking pixel to spy on victims
5. Token parameter `?token=abc123` to track individual victims

---

## Verdict

**URL: MALICIOUS — HIGH CONFIDENCE**
- Confirmed phishing by 13/91 security vendors
- Domain suspended due to malicious activity
- Tracking infrastructure actively spying on victims
---

## VirusTotal Scan Results

**Tool:** VirusTotal (virustotal.com)
**Scan Date:** June 5, 2026

| Metric          | Result                        |
|-----------------|-------------------------------|
| Detection Rate  | 10/91 security vendors        |
| Verdict         | MALICIOUS / PHISHING          |

### Vendors That Flagged:
| Vendor          | Verdict   |
|-----------------|-----------|
| BitDefender     | Phishing  |
| Kaspersky       | Phishing  |
| ESET            | Phishing  |
| Fortinet        | Phishing  |
| Sophos          | Phishing  |
| G-Data          | Phishing  |
| Lionic          | Phishing  |
| Webroot         | Malicious |
| ADMINUSLabs     | Malicious |
| Chong Lua Dao   | Malicious |

---

## URLScan.io Results

**Tool:** URLScan.io (urlscan.io)
**Scan Date:** June 5, 2026

| Metric          | Result                        |
|-----------------|-------------------------------|
| Detection Rate  | 13/91 security vendors        |
| Verdict         | MALICIOUS / PHISHING          |

### Additional Vendors Flagged:
| Vendor          | Verdict   |
|-----------------|-----------|
| alphaMountain   | Phishing  |
| CyRadar         | Phishing  |
| VIPRE           | Phishing  |

---

## Domain Investigation

**Domain:** paypal-secure-login.xyz

| Check           | Result                                    |
|-----------------|-------------------------------------------|
| Whois Status    | DOMAIN NOT FOUND — Deleted/Suspended      |
| Reason          | Flagged by multiple security vendors      |
| Real PayPal     | paypal.com (registered since 1999)        |
| Fake Domain     | paypal-secure-login.xyz (deleted)         |

---

## Tracking Pixel Found

**URL:** `http://185.220.101.47/track.php?id=victim123`

| Detail    | Value                                      |
|-----------|--------------------------------------------|
| Purpose   | 1x1 invisible pixel — tracks email opens  |
| Risk       | Reveals victim IP, location, email client |
| IP        | 185.220.101.47 (Tor exit node — Germany)  |

### How Tracking Pixel Works:
1. Victim opens email
2. Invisible image loads from attacker server
3. Attacker records: victim IP, location, device, email client
4. Attacker knows email was opened

---

## Red Flags Summary

1. Domain typosquatting — `paypal-secure-login.xyz`
2. Flagged by 13 security vendors
3. Domain completely deleted/suspended
4. Tracking pixel to spy on victims
5. Token parameter `?token=abc123` to track individual victims

---

## Verdict

**URL: MALICIOUS — HIGH CONFIDENCE**
- Confirmed phishing by 13/91 security vendors
- Domain suspended due to malicious activity
- Tracking infrastructure actively spying on victims
