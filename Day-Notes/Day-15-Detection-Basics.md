# Day 15 – Detection Basics

## Overview

Security detections help SOC analysts identify malicious or suspicious behavior from logs and telemetry. Unlike preventive controls, detections identify attacks that are in progress or have already occurred, allowing analysts to investigate and respond quickly.

---

## Learning Objectives

- Understand security detections.
- Differentiate detections from alerts.
- Learn common detection data sources.
- Explore various detection types.
- Understand the importance of detection tuning.

---

## Key Concepts

### Detection vs Alert

| Detection | Alert |
|-----------|-------|
| Rule or analytic that identifies suspicious activity | Notification generated when a detection is triggered |

### Common Detection Data Sources

- Windows Security Logs
- Sysmon
- AWS CloudTrail
- Azure Activity Logs
- Firewall Logs
- IDS/IPS
- Proxy Logs
- DNS Logs

### Detection Types

- Signature-Based
- Rule-Based
- Behavioral
- Threat Intelligence
- AI / Machine Learning

### Detection Tuning

Improve alert quality by:

- Using allowlists
- Monitoring command-line arguments
- Correlating multiple events
- Applying behavioral context
- Assigning appropriate severity

---

## Practical Exercise

Designed detections for:

- Brute-force authentication
- Encoded PowerShell
- Registry persistence
- DNS beaconing
- Outbound HTTPS communication

Improved detections by introducing:

- Parent-child process analysis
- Trusted allowlists
- Behavioral correlation
- Command-line filtering

---

## Investigation Scenario

Multiple detections identified:

- Failed authentication attempts
- Encoded PowerShell execution
- Registry persistence
- Suspicious DNS activity
- Outbound network communication

### MITRE ATT&CK

- T1110 – Brute Force
- T1059.001 – PowerShell
- T1027 – Obfuscated Files
- T1547.001 – Registry Run Keys
- T1071.004 – DNS
- T1071.001 – Web Protocols

---

## Key Takeaways

- Detections identify suspicious behavior.
- Alerts are generated when detections trigger.
- Behavioral detections improve accuracy.
- Detection tuning reduces false positives.
- Correlation provides stronger evidence than isolated events.

---

## Skills Practiced

- Detection engineering
- Rule design
- Behavioral analysis
- Alert tuning
- MITRE ATT&CK mapping

---

## Tools Used

- Windows Event Logs
- Sysmon
- ChatGPT

---

## Outcome

Developed foundational detection engineering skills and learned how well-tuned detections improve SOC effectiveness while reducing unnecessary alerts.
