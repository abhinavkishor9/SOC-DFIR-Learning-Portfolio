# Day 17 – RDP Detection Engineering

## Overview

Remote Desktop Protocol (RDP) is widely used for legitimate administration but is also a common target for attackers. This lab focused on detecting suspicious RDP activity using authentication behavior and post-login correlation.

---

## Learning Objectives

- Understand RDP authentication.
- Detect brute-force attacks.
- Identify suspicious RDP sessions.
- Correlate authentication with endpoint activity.
- Reduce false positives.

---

## Key Concepts

### Legitimate Uses

- Remote administration
- IT support
- Server management

### Common Attacker Abuse

- Brute-force attacks
- Credential stuffing
- Lateral movement
- Ransomware deployment

### Detection Opportunities

- Multiple failed logins
- Successful login after failures
- Unusual login time
- New source IP
- Privileged account login
- Suspicious post-login activity

---

## Practical Exercise

Created detections for:

- Brute-force attacks
- Successful login after failures
- Privileged account access
- New login locations
- RDP followed by PowerShell

Detection tuning included:

- Administrator allowlists
- Jump server exclusions
- VPN correlation
- Behavioral baselines

---

## Investigation Scenario

Attack chain:

Repeated Failed Logins
↓
Successful Administrator Login
↓
PowerShell
↓
New Local Account
↓
Scheduled Task
↓
HTTPS Communication

### MITRE ATT&CK

- T1110 – Brute Force
- T1078 – Valid Accounts
- T1021.001 – Remote Desktop Protocol
- T1059.001 – PowerShell
- T1136 – Create Account
- T1053.005 – Scheduled Task
- T1071.001 – Web Protocols

Severity: **Critical**

---

## Key Takeaways

- Authentication events alone are insufficient.
- Correlating post-login behavior improves detection quality.
- Baselines reduce unnecessary alerts.
- Behavioral analysis strengthens investigations.

---

## Skills Practiced

- Authentication analysis
- Detection engineering
- RDP investigation
- Event correlation
- Detection tuning

---

## Tools Used

- Windows Event Logs
- Sysmon
- ChatGPT

---

## Outcome

Developed behavior-based RDP detections capable of identifying brute-force attacks and post-authentication compromise.
