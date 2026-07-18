# Day 09 – AI Log Analysis for SOC Analysts

## Overview

Artificial Intelligence (AI) can significantly improve SOC operations by accelerating log analysis, identifying Indicators of Compromise (IoCs), correlating related events, and mapping attacker behavior to the MITRE ATT&CK framework. However, AI should be treated as an investigation assistant rather than a source of evidence. Every AI-generated finding must be validated using actual telemetry.

---

## Learning Objectives

- Understand how AI assists in security log analysis.
- Extract important fields from security logs.
- Correlate events into an attack timeline.
- Map observed behavior to MITRE ATT&CK.
- Recognize the importance of analyst validation.

---

## Key Concepts

### AI Log Analysis Workflow

Security Log
↓
Identify Source
↓
Extract Key Fields
↓
Identify IoCs
↓
Correlate Events
↓
MITRE ATT&CK Mapping
↓
Severity Assessment
↓
Investigation Recommendations
↓
Analyst Validation

### Common Security Log Sources

- Windows Security Logs
- Sysmon
- AWS CloudTrail
- Firewall Logs
- SIEM Platforms

### AI Can Help With

- Log summarization
- IoC extraction
- Event correlation
- MITRE ATT&CK mapping
- Investigation recommendations

---

## Practical Exercise

During this lab, AI was used to analyze multiple security logs.

### Windows Event ID 4625

AI identified:

- Failed authentication attempts
- Username
- Source IP
- Possible brute-force activity

### Windows Event ID 4688

AI detected:

- PowerShell spawning cmd.exe
- Possible LOLBins activity
- Recommended command-line verification

### AWS CloudTrail

AI identified:

- IAM policy modification
- Potential privilege escalation
- Need to verify authorization

### Firewall Logs

AI detected:

- Repeated SSH attempts on TCP/22
- Likely brute-force behavior

---

## Investigation Scenario

AI correlated the following attack sequence:

4625 Failed Logins
↓
4624 Successful Login
↓
PowerShell Execution
↓
cmd.exe
↓
whoami
↓
IAM Policy Modification

### MITRE ATT&CK

- T1110 — Brute Force
- T1078 — Valid Accounts
- T1059.001 — PowerShell
- T1059.003 — Windows Command Shell
- T1033 — System Owner/User Discovery
- T1098 — Account Manipulation

Severity Assessment: **High** (pending analyst validation)

---

## Key Takeaways

- AI significantly speeds up log triage.
- Event correlation provides stronger evidence than isolated logs.
- MITRE mapping improves investigations.
- Better prompts produce better analysis.
- Analysts must always validate AI-generated findings.

---

## Skills Practiced

- AI-assisted log analysis
- IoC extraction
- Event correlation
- MITRE ATT&CK mapping
- Investigation prioritization

---

## Tools Used

- ChatGPT
- Windows Event Logs
- AWS CloudTrail
- Firewall Logs

---

## Outcome

Successfully used AI to analyze multiple log sources, correlate events into an attack timeline, and understand why analyst validation remains essential during SOC investigations.
