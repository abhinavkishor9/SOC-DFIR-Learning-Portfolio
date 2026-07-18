# Day 24 – Wazuh Brute Force Detection

## Overview

Brute-force attacks target authentication systems by repeatedly attempting passwords until successful access is obtained. This lab focused on detecting brute-force attacks using Windows authentication events collected by Wazuh.

---

## Learning Objectives

- Understand brute-force attacks.
- Analyze Windows authentication events.
- Learn Wazuh threshold-based detection.
- Correlate authentication with endpoint activity.
- Investigate suspected compromises.

---

## Key Concepts

### Important Authentication Events

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

Logon Type 10 indicates Remote Desktop authentication.

### Detection Workflow

Authentication Attempt

↓

Windows Security Log

↓

Event ID 4624 / 4625

↓

Wazuh Agent

↓

Manager Rules

↓

Brute Force Alert

↓

SOC Investigation

---

## Practical Exercise

Observed:

- Multiple failed logins
- Successful RDP login
- PowerShell execution
- Certutil execution
- HTTPS communication

Reviewed authentication patterns using Wazuh.

---

## Investigation Scenario

Attack sequence:

- Five failed logins
- Successful RDP authentication
- PowerShell execution
- Certutil activity
- Outbound HTTPS connection

### MITRE ATT&CK

- T1110 – Brute Force
- T1021.001 – Remote Desktop Protocol
- T1059.001 – PowerShell
- T1218.010 – Certutil
- T1071.001 – Web Protocols

---

## Key Takeaways

- Threshold-based detections reduce false positives.
- Successful login after repeated failures deserves investigation.
- Authentication should be correlated with endpoint behavior.
- MITRE mapping improves documentation.

---

## Skills Practiced

- Authentication analysis
- Wazuh threat hunting
- Brute-force detection
- Event correlation
- MITRE ATT&CK mapping

---

## Tools Used

- Windows Security Logs
- Wazuh Dashboard

---

## Outcome

Developed practical experience detecting brute-force attacks using authentication telemetry and behavioral correlation.
