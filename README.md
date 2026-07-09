# University Student Portal — Web Security Audit

## Purpose
Authorized web application penetration test conducted on a university 
student portal as part of a cybersecurity internship, to identify 
vulnerabilities before they could be exploited by a real attacker.

## Scope
Web application penetration testing covering authentication, session 
management, input handling, and transport-layer security configuration.

## Summary
Testing identified multiple vulnerabilities affecting session integrity, 
user input handling, and secure transport enforcement. Findings were 
reported to university officials with remediation recommendations.

## Findings Summary

| Finding                                  | Category              | Severity |
|-------------------------------------------|------------------------|----------|
| SQL Injection (session parameter)         | Injection              | Critical |
| Reflected Cross-Site Scripting (XSS)      | Injection              | High     |
| Session Cookie Missing Secure Flag        | Session Management      | Medium   |
| HTTP Strict Transport Security Not Enforced | Transport Security    | Medium   |

## Methodology
Testing followed standard web application penetration testing practice, 
aligned with the OWASP Top 10, covering request/response analysis with 
Burp Suite, manual parameter testing, and session/cookie inspection.

## Key Findings (Generalized)
- **SQL Injection:** A session-related parameter was found to accept 
  unsanitized input, creating risk of session fixation or unauthorized 
  data access.
- **Reflected XSS:** A URL parameter reflected user input directly into 
  the page without sanitization, allowing injection of malicious scripts 
  via crafted links.
- **Insecure Cookie Flag:** Session cookies were transmitted without the 
  `Secure` flag, allowing potential interception over unencrypted 
  connections.
- **Missing HSTS:** The application did not enforce HTTPS via HSTS, 
  leaving it exposed to protocol downgrade and MITM attacks.

## Report
Full report with detailed findings, evidence, and remediation guidance 
available in [`report.docx`](./report.docx) *(available on request / 
redacted version)*.

## Disclosure Note
This assessment was conducted with authorization as part of an official 
university cybersecurity internship. Specific target details and 
exploit payloads have been generalized in this public write-up. Full 
technical details were disclosed privately to university officials.
