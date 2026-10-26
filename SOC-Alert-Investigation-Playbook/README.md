# SOC Alert & Attack Investigation Playbooks

A structured learning and portfolio repository for SOC analysts. Each scenario has two files:
- `<Alert-Name>.md` — detailed alert/attack explanation, triage workflow, evidence checklist, possible conclusions, response guidance and interview practice.
- `<Alert-Name>KQL.kql` — investigation queries followed by a **Master KQL** section at the end.

**Author:** Zeeshan Alam · [LinkedIn](https://www.linkedin.com/in/zeeshanalam21/) · [GitHub](https://github.com/Zeeshan2374)

## Repository principles
- An alert is an investigation lead, not automatic proof of compromise.
- Query schemas and fields vary by Microsoft Sentinel workspace, Defender XDR tables, licensing and data ingestion. Validate queries before operational use.
- Use synthetic or authorized lab data only. Do not commit customer data, credentials, tenant secrets or confidential screenshots.
- Master queries provide consolidated triage where practical; investigations that require multiple data sources still need separate pivots and validation.

## Playbook index
- [Impossible Travel](01-Identity-and-Authentication/Impossible-Travel/Impossible-Travel.md) — `Identity and Authentication`
- [Password Spraying](01-Identity-and-Authentication/Password-Spraying/Password-Spraying.md) — `Identity and Authentication`
- [Brute-Force Attack](01-Identity-and-Authentication/Brute-Force-Attack/Brute-Force-Attack.md) — `Identity and Authentication`
- [Suspicious MFA Activity](01-Identity-and-Authentication/Suspicious-MFA-Activity/Suspicious-MFA-Activity.md) — `Identity and Authentication`
- [Mailbox Permission Change](02-Email-and-Microsoft-365/Mailbox-Permission-Change/Mailbox-Permission-Change.md) — `Email and Microsoft 365`
- [Suspicious Inbox Forwarding Rules](02-Email-and-Microsoft-365/Inbox-Forwarding-Rules/Suspicious-Inbox-Forwarding-Rules.md) — `Email and Microsoft 365`
- [Phishing Investigation](02-Email-and-Microsoft-365/Phishing-Investigation/Phishing-Investigation.md) — `Email and Microsoft 365`
- [Suspicious OAuth Consent](02-Email-and-Microsoft-365/Suspicious-OAuth-Consent/Suspicious-OAuth-Consent.md) — `Email and Microsoft 365`
- [Threat Intelligence IP Match in Sign-in Logs](03-Threat-Intelligence/TI-Map-Entity-to-SigninLogs/Threat-Intelligence-IP-Match-in-Sign-in-Logs.md) — `Threat Intelligence`
- [Malicious IP Activity](03-Threat-Intelligence/Malicious-IP-Activity/Malicious-IP-Activity.md) — `Threat Intelligence`
- [Possible DGA Domain Contact](03-Threat-Intelligence/DGA-Domain-Detection/Possible-DGA-Domain-Contact.md) — `Threat Intelligence`
- [Suspicious PowerShell Execution](04-Endpoint-Attacks/Suspicious-PowerShell/Suspicious-PowerShell-Execution.md) — `Endpoint Attacks`
- [Suspicious Process Execution](04-Endpoint-Attacks/Suspicious-Process-Execution/Suspicious-Process-Execution.md) — `Endpoint Attacks`
- [Encoded Command Execution](04-Endpoint-Attacks/Encoded-Command-Execution/Encoded-Command-Execution.md) — `Endpoint Attacks`
- [Credential Access Indicators](04-Endpoint-Attacks/Credential-Access-Indicators/Credential-Access-Indicators.md) — `Endpoint Attacks`
- [Unexpected Privileged Role Change](05-Cloud-and-Privilege-Attacks/Privileged-Role-Change/Unexpected-Privileged-Role-Change.md) — `Cloud and Privilege`
- [Suspicious Account Creation or Modification](05-Cloud-and-Privilege-Attacks/Account-Creation-Changes/Suspicious-Account-Creation-or-Modification.md) — `Cloud and Privilege`
- [Unusual Azure Activity](05-Cloud-and-Privilege-Attacks/Unusual-Azure-Activity/Unusual-Azure-Activity.md) — `Cloud and Privilege`
- [Suspicious DNS Activity](06-Network-Threats/Suspicious-DNS-Activity/Suspicious-DNS-Activity.md) — `Network Threats`
- [Possible Command-and-Control Activity](06-Network-Threats/Command-and-Control-Indicators/Possible-Command-and-Control-Activity.md) — `Network Threats`
- [Malware Detection](07-Malware-and-Persistence/Malware-Detection/Malware-Detection.md) — `Malware and Persistence`
- [Suspicious Persistence Mechanism](07-Malware-and-Persistence/Persistence-Mechanism/Suspicious-Persistence-Mechanism.md) — `Malware and Persistence`
- [Ransomware Indicators](07-Malware-and-Persistence/Ransomware-Indicators/Ransomware-Indicators.md) — `Malware and Persistence`
- [Possible Lateral Movement](07-Malware-and-Persistence/Lateral-Movement/Possible-Lateral-Movement.md) — `Malware and Persistence`

## Suggested workflow
1. Read the Markdown guide.
2. Run the initial query in an authorized lab or workspace.
3. Inspect the Master KQL section at the end of the KQL file.
4. Correlate other tables and investigate false positives.
5. Record evidence, conclusion and response actions.

## Disclaimer
These materials are for education and authorized defensive security work. They are not a substitute for your organisation's incident-response policy or Microsoft documentation.

## Connect with me
- LinkedIn: [linkedin.com/in/zeeshanalam21](https://www.linkedin.com/in/zeeshanalam21/)
- GitHub: [github.com/Zeeshan2374](https://github.com/Zeeshan2374)
