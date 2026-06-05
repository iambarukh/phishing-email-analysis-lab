# Phishing Email Analysis — Final Investigation Report

**Analyst:** Aswad
**Date:** June 5, 2026
**Classification:** Educational / Portfolio Project
**Severity:** HIGH — Active Phishing Campaign Identified

---

## 1. Executive Summary

This report documents the investigation of a real-world phishing email
sample targeting PayPal users. The email was analyzed using seven
industry-standard cybersecurity tools including email header analyzers,
IP reputation services, URL scanners, and sandbox environments.

### Key Findings:
- Email failed all authentication checks (SPF, DKIM, DMARC)
- Sender IP flagged with 100% abuse confidence (6,561 reports)
- Malicious URL detected by 13/91 security vendors
- Domain suspended due to malicious activity
- Sandbox confirmed network threat and suspicious child process
- Tor exit node used to hide attacker identity

---

## 2. Sample Information

| Field          | Value                           |
|----------------|---------------------------------|
| File           | phishing-sample-01.eml          |
| MD5            | ad951d13053484cadab5c5d496937aed|
| Target Brand   | PayPal                          |
| Attack Type    | Credential Phishing             |
| Threat Level   | HIGH                            |
| Status         | Domain Suspended/Deleted        |

---

## 3. Email Header Analysis

### Authentication Results

| Check | Result | Detail                                  |
|-------|--------|-----------------------------------------|
| SPF   | FAIL   | IP not authorized for paypa1-secure.com |
| DKIM  | FAIL   | No valid DKIM signature found           |
| DMARC | FAIL   | No DMARC policy on domain              |

**Tool Used:** MXToolbox
**Key Finding:** IP 185.220.101.47 found on blacklist

### Red Flags in Header

| Field          | Value                  | Why Suspicious              |
|----------------|------------------------|-----------------------------|
| From domain    | paypa1-secure.com      | Typosquat — 1 not l         |
| X-Mailer       | PHPMailer 5.2.0        | Bulk spam tool              |
| Originating IP | 185.220.101.47         | Tor exit node — blacklisted |
| Subject        | URGENT: Account...     | Fear/urgency tactic         |

---

## 4. URL Analysis

### Malicious URL
http://paypal-secure-login.xyz/verify?token=abc123
### Scan Results

| Tool       | Detection      | Verdict   |
|------------|----------------|-----------|
| VirusTotal | 10/91 vendors  | Malicious |
| URLScan.io | 13/91 vendors  | Phishing  |
| Whois      | Domain deleted | Suspended |

### Tracking Pixel
http://185.220.101.47/track.php?id=victim123
---

## 8. Attack Flow
Step 1: Victim receives email from paypa1-secure.com
↓
Step 2: Subject line creates fear — "Account Suspended"
↓
Step 3: Victim opens email — tracking pixel fires
↓
Step 4: Attacker records victim IP and device info
↓
Step 5: Victim clicks malicious link
↓
Step 6: Fake PayPal login page loads
↓
Step 7: Victim enters credentials
↓
Step 8: Credentials stolen — sent to attacker server
↓
Step 9: Victim redirected to real PayPal (no suspicion)
---

## 9. Recommendations

### For Organizations:
1. Enforce DMARC policy with p=reject on all domains
2. Deploy email security gateway (Proofpoint/Mimecast)
3. Block newly registered domains under 30 days old
4. Train employees on phishing awareness quarterly
5. Implement hardware security keys (FIDO2/YubiKey)

### For End Users:
1. Never click links in urgent/alarming emails
2. Check domain carefully — paypa1 is NOT paypal
3. Type website URL manually in browser
4. Report suspicious emails to security team
5. Enable hardware 2FA instead of SMS

---

## 10. Conclusion

This investigation confirms a high-confidence phishing campaign
targeting PayPal users. The attacker used multiple sophisticated
techniques including domain typosquatting, Tor infrastructure,
tracking pixels, and social engineering. All seven analysis tools
confirmed malicious activity. The domain has since been suspended,
indicating the security community successfully identified and
neutralized this threat.

**Final Verdict: PHISHING — HIGH CONFIDENCE**

---

## 11. Tools & References

| Tool       | URL                  |
|------------|----------------------|
| PhishTank  | phishtank.org        |
| MXToolbox  | mxtoolbox.com        |
| VirusTotal | virustotal.com       |
| URLScan.io | urlscan.io           |
| AbuseIPDB  | abuseipdb.com        |
| Any.run    | app.any.run          |
| Whois      | Linux terminal       |

---

*Report prepared for educational and portfolio purposes.*
*Analyst: Aswad | GitHub: [Your GitHub URL]*