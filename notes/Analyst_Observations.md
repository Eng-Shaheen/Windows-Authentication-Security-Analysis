# Analyst Observations – Windows Authentication Security Analysis

## Investigation Context
During routine review of Windows Security logs, authentication-related events were analyzed to identify potential unauthorized access attempts and validate normal user behavior.

The investigation focused on successful logons, failed authentication attempts, and session termination events.

---

## Key Observations

### Failed Authentication Activity
Multiple Event ID **4625** entries were observed, indicating failed logon attempts due to invalid credentials.

These events are commonly associated with:
- Password guessing
- Brute-force attempts
- Misconfigured services or users

The presence of repeated failures raises the risk of credential-based attacks.

---

### Successful Authentication Events
Event ID **4624** entries confirmed successful logons.

These events were reviewed to:
- Establish baseline access behavior
- Identify successful logons following prior failures
- Validate authentication mechanisms and logon types

A successful logon after repeated failures would significantly increase compromise likelihood.

---

### Session Lifecycle Validation
Event ID **4634** events confirmed user session terminations.

Logoff events were used to:
- Track session duration
- Support timeline-based analysis
- Validate proper session closure after authentication

---

## Threat Assessment

**Severity:** Medium  

While failed authentication attempts were detected, no direct evidence of account compromise was observed in this dataset. However, continued monitoring and correlation with other log sources would be required to rule out escalation.

---

## MITRE ATT&CK Mapping
- **T1110 – Brute Force**  
  Evidence: Repeated failed authentication attempts (Event ID 4625)

- **T1078 – Valid Accounts**  
  Evidence: Successful logon events (Event ID 4624)

---

## SOC Value
This analysis demonstrates the ability to:
- Triage Windows authentication logs
- Identify suspicious login behavior
- Correlate authentication events across session lifecycles
- Document findings in a SOC-ready investigation format

---

## Analyst Notes
All evidence was reviewed using sanitized log data. No user identifiers, hostnames, or credentials were exposed during analysis or documentation.
