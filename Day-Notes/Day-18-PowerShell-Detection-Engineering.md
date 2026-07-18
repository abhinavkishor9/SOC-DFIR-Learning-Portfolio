# Day 18 – PowerShell Detection Engineering

## Overview

PowerShell is an essential Windows administration tool but is also one of the most abused Living-off-the-Land Binaries (LOLBins). This lab focused on detecting malicious PowerShell activity while reducing false positives.

---

## Learning Objectives

- Understand legitimate PowerShell usage.
- Detect malicious PowerShell execution.
- Identify download cradles.
- Improve detection fidelity.
- Correlate PowerShell with endpoint activity.

---

## Key Concepts

### Legitimate Uses

- Automation
- Active Directory administration
- Azure management
- Software deployment

### Common Attacker Abuse

- Encoded commands
- Download cradles
- Fileless malware
- Persistence
- C2 communication

### Detection Opportunities

- EncodedCommand
- ExecutionPolicy Bypass
- Hidden PowerShell
- Invoke-WebRequest
- DownloadString
- IEX

---

## Practical Exercise

Developed detections for:

- Encoded commands
- Hidden PowerShell
- Download cradles
- ExecutionPolicy Bypass
- Network communication

Detection tuning included:

- Script Block Logging
- Module Logging
- Parent-process analysis
- Administrative allowlists
- Multi-event correlation

---

## Investigation Scenario

Attack chain:

Successful Login
↓
Encoded PowerShell
↓
Payload Download
↓
Payload Execution
↓
Scheduled Task
↓
HTTPS Communication

### MITRE ATT&CK

- T1078 – Valid Accounts
- T1059.001 – PowerShell
- T1027 – Obfuscated Files
- T1105 – Ingress Tool Transfer
- T1204 – User Execution
- T1053.005 – Scheduled Task
- T1071.001 – Web Protocols

Severity: **Critical**

---

## Key Takeaways

- PowerShell should be monitored using behavior rather than process name.
- Script Block Logging provides valuable visibility.
- Correlation significantly improves detection quality.
- Detection tuning reduces false positives.

---

## Skills Practiced

- PowerShell detection engineering
- Endpoint monitoring
- Threat hunting
- Event correlation
- Detection tuning

---

## Tools Used

- Sysmon
- Windows Event Logs
- PowerShell
- ChatGPT

---

## Outcome

Designed robust PowerShell detections capable of identifying modern fileless attacks while minimizing false positives.
