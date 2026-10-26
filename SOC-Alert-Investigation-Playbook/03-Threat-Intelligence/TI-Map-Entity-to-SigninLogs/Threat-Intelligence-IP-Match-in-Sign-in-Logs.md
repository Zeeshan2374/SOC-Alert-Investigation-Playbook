# Threat Intelligence IP Match in Sign-in Logs — SOC Investigation Guide

## 1. What Does This Alert Mean?
A sign-in IP matches a threat-intelligence indicator. The match requires validation of indicator quality, age, confidence and authentication outcome.

**Important:** An alert is an investigation lead, not automatic proof of compromise. Reach a conclusion using corroborating evidence and the environment's normal behaviour.

## 2. Why It Matters
Potential security impact may include unauthorized access, data exposure, persistence, privilege abuse or further compromise, depending on the evidence and the asset involved.

## 3. Possible Benign Explanations / False Positives
- Stale or low-confidence indicator; shared hosting/VPN; benign shared infrastructure; incorrect indicator context.

## 4. Step-by-Step Investigation
### Step 1 — Capture source IP, user, app, timestamp and authentication result
Capture source IP, user, app, timestamp and authentication result.
### Step 2 — Validate indicator source, confidence, expiry and type
Validate indicator source, confidence, expiry and type.
### Step 3 — Search the IP across other users and telemetry
Search the IP across other users and telemetry.
### Step 4 — If sign-in succeeded, review device, MFA, mailbox and cloud activity
If sign-in succeeded, review device, MFA, mailbox and cloud activity.

## 5. Indicators That Increase Concern
- Successful authentication from a high-confidence malicious IP
- Same IP targets many users
- Related suspicious post-authentication activity

## 6. Evidence Checklist
- [ ] Alert name, severity, timestamp and detection source
- [ ] Affected user, host, IP, application, resource or mailbox
- [ ] Relevant time window and surrounding events
- [ ] Source, destination and process/account context where applicable
- [ ] Authentication, permission, result or remediation status
- [ ] Related alerts and other affected entities
- [ ] Business context, owner confirmation and change ticket if applicable
- [ ] Evidence supporting benign, suspicious or potential-compromise classification

## 7. Possible SOC Conclusions

### Benign / Expected
The activity is explained by approved business activity or known infrastructure, and no corroborating suspicious evidence is found. Document the evidence and close according to policy.

### Suspicious / Needs More Investigation
The activity is unusual or lacks a clear business explanation, but evidence is insufficient to confirm compromise. Enrich the evidence, expand the scope and escalate as required.

### Potential Compromise
Multiple independent indicators support unauthorized activity. Preserve evidence and follow the organisation's incident-response, containment and communication procedures.

## 8. Response Guidance
1. Preserve alert details, query results and timestamps.
2. Determine scope and business impact before taking disruptive action.
3. Escalate to the appropriate incident owner when the evidence or severity warrants it.
4. Follow approved containment, credential, endpoint or cloud-response procedures.
5. Record the rationale, actions, outcome and lessons learned.

## 9. Companion KQL File
Use [`Threat-Intelligence-IP-Match-in-Sign-in-LogsKQL.kql`](./Threat-Intelligence-IP-Match-in-Sign-in-LogsKQL.kql) for investigation queries and a final Master Investigation Query. Confirm the data source and schema before operational use.

## 10. Interview Practice
**Q: Does this alert automatically mean an attack occurred?**  
A: No. I treat it as an investigation trigger, validate the affected entity and timeline, check legitimate explanations, correlate supporting telemetry, and classify the result based on evidence.

**Q: What would you investigate first?**  
A: I would establish who or what is affected, what event triggered the alert, when it happened, which related entities are involved, and whether the activity was successful. I would then expand the timeline and check for corroborating indicators.

**Q: How do you decide whether to escalate?**  
A: I escalate when evidence, impact or uncertainty meets the organisation's escalation criteria, particularly when multiple independent indicators suggest unauthorized access or continuing risk.

## 11. Analyst Notes
- Document assumptions and any telemetry gaps.
- Avoid treating a single indicator as conclusive.
- Use least-disruptive approved response actions.
- Update this guide as schemas, detections and platform capabilities change.
