# Day 10 – Sysmon Analysis

## Overview

Sysmon (System Monitor) extends Windows logging by capturing detailed endpoint telemetry including process creation, network connections, registry changes, file creation, and DNS activity. These events provide valuable visibility for SOC analysts during malware investigations and threat hunting.

---

## Learning Objectives

- Understand the purpose of Sysmon.
- Learn important Sysmon Event IDs.
- Analyze endpoint telemetry.
- Correlate multiple Sysmon events.
- Map endpoint activity to MITRE ATT&CK.

---

## Key Concepts

### What is Sysmon?

Sysmon is a Microsoft Sysinternals tool that records detailed endpoint activity beyond standard Windows Security Logs.

Unlike authentication-focused Windows logs, Sysmon captures process behavior, network activity, persistence mechanisms, and DNS activity.

### Important Sysmon Event IDs

| Event ID | Description |
|----------|-------------|
| 1 | Process Creation |
| 3 | Network Connection |
| 11 | File Creation |
| 13 | Registry Value Set |
| 22 | DNS Query |

---

## Common Detection Use Cases

- Encoded PowerShell
- LOLBins
- Malware persistence
- Registry Run Keys
- Command-and-Control communication
- DNS beaconing

---

## Investigation Workflow

Process Creation
↓
Network Connection
↓
DNS Resolution
↓
Registry Persistence
↓
MITRE ATT&CK Mapping
↓
Threat Validation

---

## Practical Exercise

### Event ID 1 – Process Creation

Observed:

- PowerShell executing EncodedCommand
- Possible command obfuscation
- Base64 payload requiring decoding

### Event ID 3 – Network Connection

Observed:

- PowerShell creating outbound HTTPS connection
- Possible malware C2 communication

### Event ID 13 – Registry Persistence

Observed:

- Run Registry Key modification
- Executable launched from AppData\Roaming
- Common persistence technique

### Event ID 22 – DNS Query

Observed:

- Repeated DNS queries
- Potential beaconing behavior
- Domain reputation validation recommended

---

## Investigation Scenario

AI correlated the following sequence:

Encoded PowerShell
↓
DNS Query
↓
HTTPS Connection
↓
Registry Persistence
↓
Repeated DNS Beaconing

### MITRE ATT&CK Mapping

- T1059.001 — PowerShell
- T1027 — Obfuscated Files
- T1547.001 — Registry Run Keys
- T1036 — Masquerading
- T1071 — Application Layer Protocol
- T1568 — Dynamic Resolution
- T1041 — Exfiltration Over C2 Channel

Severity Assessment: **Critical**

---

## Key Takeaways

- Sysmon provides significantly better endpoint visibility than Windows Security Logs.
- Multiple Sysmon events should always be correlated.
- AI accelerates endpoint investigations.
- Registry persistence and repeated DNS activity are valuable detection opportunities.
- Validate suspicious domains, IPs, hashes, and processes before escalation.

---

## Skills Practiced

- Sysmon event analysis
- Endpoint telemetry investigation
- Event correlation
- MITRE ATT&CK mapping
- Threat hunting fundamentals

---

## Tools Used

- Sysmon
- Windows Event Viewer
- ChatGPT

---

## Outcome

Successfully analyzed multiple Sysmon Event IDs, correlated endpoint activity into a potential attack chain, and understood how endpoint telemetry improves SOC investigations.
