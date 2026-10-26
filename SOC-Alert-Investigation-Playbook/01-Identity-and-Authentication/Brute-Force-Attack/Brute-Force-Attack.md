# Brute-Force Attack — SOC Investigation Guide

## 1. What Does This Alert Mean?
Repeated authentication attempts target one or more accounts in an effort to guess credentials.

**Important:** An alert is an investigation lead, not automatic proof of compromise. Reach a conclusion using corroborating evidence and the environment's normal behaviour.

## 2. Why It Matters
Potential security impact may include unauthorized access, data exposure, persistence, privilege abuse or further compromise, depending on the evidence and the asset involved.

## 3. Possible Benign Explanations / False Positives
- User typo; broken service using an old password; automated legitimate integration; shared NAT.

## 4. Step-by-Step Investigation
### Step 1 — Group failures by account, IP, application and time window
Group failures by account, IP, application and time window.
### Step 2 — Review result codes and whether attempts are interactive
Review result codes and whether attempts are interactive.
### Step 3 — Check for successful authentication after the failure burst
Check for successful authentication after the failure burst.
### Step 4 — Correlate endpoint, MFA and account-change events
Correlate endpoint, MFA and account-change events.

## 5. Indicators That Increase Concern
- High-volume failures against one account
- Successful sign-in immediately after a failure burst
- Unrecognized source followed by suspicious activity

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
Use [`Brute-Force-AttackKQL.kql`](./Brute-Force-AttackKQL.kql) for investigation queries and a final Master Investigation Query. Confirm the data source and schema before operational use.

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
