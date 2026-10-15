# Phishing Email Investigation & Incident Response

## Project Overview

This project demonstrates a structured SOC analyst workflow for triaging a suspected phishing incident, assessing severity, documenting findings, identifying evidence requirements, and recommending incident response actions.

**Environment:** Simulated incident  
**Incident date:** 6 October 2026  
**Initial severity:** High  
**Disposition:** Escalate for investigation and containment

## 1. Incident Scenario

A security team receives an alert after employees report a suspicious email impersonating Microsoft IT support. The reported activity suggests possible credential theft, unauthorized mailbox changes, and potential exposure of customer information.

The following events are reported in the simulated scenario:

- 25 employees received the suspicious email.
- Three recipients clicked the link.
- One recipient reportedly submitted Microsoft 365 credentials.
- A successful sign-in from an unfamiliar IP address was reported.
- A new mailbox forwarding rule appeared.
- An outbound email containing a customer spreadsheet was reportedly sent to 40 external recipients.

These events require validation against source records before compromise or data exposure can be considered confirmed.

## 2. Alert Triage

| Field | Assessment |
|---|---|
| Alert type | Suspected phishing / account compromise |
| Reported source | `it-support@micr0soft-example.com` |
| Suspicious URL | `https://company-example.com.security-check.example.net/login` |
| Recipients | 25 |
| Reported clicks | 3 |
| Reported credential submissions | 1 |
| Potential impact | Unauthorized account access and customer-data exposure |
| Severity | High |
| Classification | True positive for the simulated scenario; real-world activity requires validation |
| Recommended disposition | Escalate and investigate urgently |

### Why High Severity?

The combination of reported credential submission, unfamiliar sign-in activity, a new forwarding rule, and possible external transmission of customer information indicates potential account compromise and data exposure.

## 3. Initial Investigation

**Phishing indicators**
- Sender domain contains a character substitution: `micr0soft-example.com` uses a zero instead of the letter “o”.
- The message reportedly creates urgency by threatening account suspension within 30 minutes.
- The link directs users to a suspicious login URL.

**Potential account compromise**
- A user reportedly submitted credentials on the suspicious page.
- An unfamiliar successful sign-in was reported.
- A new mailbox forwarding rule may indicate an attempt to maintain access or monitor email.

**Potential data exposure**
- An email containing customer names, phone numbers, and account balances was reportedly sent to external recipients.
- Delivery, access, and the extent of any disclosure have not been independently verified.

**Investigation status:** Preliminary. Source evidence has not yet been collected or validated.

## 4. The Five Ws

**Who?**  
Twenty-five employees reportedly received the email. Three reportedly clicked the link, and one reportedly submitted credentials.

**What?**  
A suspected phishing incident may have resulted in account compromise, mailbox manipulation, and exposure of customer information.

**When?**  
6 October 2026, between 08:42 and 09:05 East Africa Time (EAT).

**Where?**  
The email system, suspicious login webpage, reported sign-in activity, mailbox forwarding configuration, and outbound email.

**Why?**  
The suspected objective may have been to steal credentials, gain mailbox access, and obtain or disclose customer information. The actor's actual intent remains unverified.

## 5. Recommended Response Actions

1. **Contain:** Revoke active sessions and reset the affected user's credentials through the approved process.
2. **Secure access:** Review MFA settings, authentication methods, sign-in history, and other signs of unauthorized access.
3. **Investigate the mailbox:** Preserve relevant audit evidence, examine the forwarding rule, and remove it when appropriate.
4. **Limit phishing impact:** Identify recipients and clickers, quarantine or remove the message where possible, and check for other affected accounts.
5. **Investigate possible disclosure:** Review message trace records, external recipients, delivery status, and the contents of the attachment.
6. **Escalate:** Notify the appropriate security, privacy, legal, and compliance teams to assess impact and any applicable reporting obligations.
7. **Document:** Record the evidence collected, actions taken, decisions made, and outstanding questions.

## 6. Evidence Required

The investigation should collect and preserve the original email and headers, message authentication results, URL details, click telemetry, sign-in records, mailbox audit logs, forwarding-rule details, outbound message trace records, and incident response action logs.

See `evidence/evidence-register.csv` for the evidence collection checklist and `evidence/incident-timeline.csv` for the reported event sequence.

## 7. Conclusion

The simulated case warrants high-priority investigation because it combines suspected phishing, possible credential compromise, suspicious mailbox activity, and potential customer-data exposure.

The appropriate response is to contain the suspected account compromise, preserve evidence, determine the scope of affected users and information, and escalate according to the organization's incident response procedures.

**Important limitation:** This is a scenario-based investigation exercise. No real email headers, authentication logs, mailbox audit records, or message trace records were collected. Reported events are not presented as independently verified findings.