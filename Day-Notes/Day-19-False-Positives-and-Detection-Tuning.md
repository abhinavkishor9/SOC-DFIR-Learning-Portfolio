# Day 19 – False Positives & Detection Tuning

## Overview

Detection engineering is not only about identifying malicious activity but also about minimizing unnecessary alerts. This lab focused on understanding false positives and applying tuning techniques to improve detection quality.

---

## Learning Objectives

- Understand alert classification.
- Identify causes of false positives.
- Learn detection tuning techniques.
- Improve alert fidelity.
- Reduce analyst fatigue.

---

## Key Concepts

### Alert Classification

| Classification | Description |
|---------------|-------------|
| True Positive | Malicious activity correctly detected |
| False Positive | Legitimate activity incorrectly flagged |
| True Negative | Legitimate activity ignored |
| False Negative | Malicious activity missed |

### Common Causes of False Positives

- Broad detection rules
- Legitimate administrator activity
- Software deployment
- Security tools
- Missing behavioral context

### Detection Tuning

- Trusted allowlists
- Event thresholds
- Behavioral baselines
- Command-line analysis
- Multi-event correlation

---

## Practical Exercise

Analyzed false positives involving:

- PowerShell
- Certutil
- RDP
- Scheduled Tasks
- Windows Defender

Improved detections using:

- Administrative allowlists
- User behavior baselines
- Command-line analysis
- Event thresholds
- Correlation

---

## Investigation Scenario

Alerts generated for:

- PowerShell
- Certutil
- RDP
- Scheduled Tasks
- Windows Defender

Investigation confirmed legitimate administrative activity, demonstrating the importance of context and behavioral analysis.

### MITRE ATT&CK

- T1059.001 – PowerShell
- T1218 – Certutil
- T1021.001 – RDP
- T1053.005 – Scheduled Task
- T1110 – Brute Force
- T1078 – Valid Accounts

---

## Key Takeaways

- Not every alert represents malicious activity.
- Behavioral context is essential.
- Event correlation improves confidence.
- Detection tuning reduces SOC workload.
- Continuous refinement improves detection quality.

---

## Skills Practiced

- Alert validation
- Detection tuning
- Behavioral analysis
- False-positive reduction
- Investigation methodology

---

## Tools Used

- Windows Event Logs
- Sysmon
- ChatGPT

---

## Outcome

Learned how effective tuning improves detection quality, reduces analyst fatigue, and enables more efficient SOC operations.
