# Email Header Analysis — Sample 01 (PayPal Phishing)

## Basic Information

| Field          | Value                      | Verdict         |
|----------------|----------------------------|-----------------|
| From           | security@paypa1-secure.com | FAKE (typosquat)|
| To             | victim@example.com         | Target          |
| Subject        | URGENT: Your PayPal...     | Urgency Tactic  |
| Date           | Mon, 02 Jun 2026           | Normal          |
| Originating IP | 185.220.101.47             | MALICIOUS       |
| X-Mailer       | PHPMailer 5.2.0            | Spam Tool       |

---

## SPF / DKIM / DMARC Results

| Check | Result | Explanation                              |
|-------|--------|------------------------------------------|
| SPF   | FAIL   | IP not authorized for paypa1-secure.com  |
| DKIM  | FAIL   | No valid DKIM signature found            |
| DMARC | FAIL   | No DMARC policy on domain               |

**Tool Used:** MXToolbox (mxtoolbox.com)

**Result:** IP 185.220.101.47 flagged — IS ON BLACKLIST

---

## Red Flags Found

### 1. Domain Typosquatting
- Fake domain: `paypa1-secure.com`
- Real domain: `paypal.com`
- Trick: Letter "l" replaced with number "1"
- This is called TYPOSQUATTING attack

### 2. Blacklisted IP Address
- IP: `185.220.101.47`
- Status: ON BLACKLIST (MXToolbox confirmed)
- AbuseIPDB: 100% abuse confidence
- Reported: 6,561 times
- Type: Tor Exit Node (Germany/Berlin)

### 3. Suspicious X-Mailer
- Value: `PHPMailer 5.2.0`
- Meaning: Old bulk email/spam tool
- Legitimate companies use proper mail servers

### 4. Urgency Tactic (Social Engineering)
- "URGENT" in subject line
- "24 hours or account closed"
- Purpose: Panic victim into clicking without thinking

---

## IP Investigation Results

**IP: 185.220.101.47**

| Tool      | Result                            |
|-----------|-----------------------------------|
| MXToolbox | Blacklisted                       |
| AbuseIPDB | 100% abuse confidence — 6561 reports |
| Location  | Berlin, Germany                   |
| ISP       | Network for Tor-Exit traffic      |
| ASN       | AS60729                           |
| Type      | Tor Exit Node                     |

---

## Verdict

**PHISHING EMAIL — HIGH CONFIDENCE**

This email is a phishing attempt impersonating PayPal using:
- Domain typosquatting (paypa1 vs paypal)
- Blacklisted IP address (Tor exit node)
- Failed SPF/DKIM/DMARC authentication
- Social engineering (urgency + fear tactics)
- PHPMailer spam tool
