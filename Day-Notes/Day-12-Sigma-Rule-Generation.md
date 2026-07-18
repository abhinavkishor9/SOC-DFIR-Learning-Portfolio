# Day 12 – Sigma Rule Generation

## Overview

Sigma is an open-source, vendor-independent detection rule format that enables security teams to create reusable detections across multiple SIEM platforms. It standardizes detection engineering and simplifies sharing detection logic.

---

## Learning Objectives

- Understand Sigma rule structure.
- Learn how to write detection logic.
- Map detections to MITRE ATT&CK.
- Reduce false positives.
- Appreciate the importance of rule validation.

---

## Key Concepts

### Core Components of a Sigma Rule

- Title
- Description
- Log Source
- Detection Logic
- Investigation Fields
- Severity
- MITRE ATT&CK Mapping
- False Positive Reduction

### Benefits of Sigma

- Vendor independent
- Reusable detection logic
- Easier collaboration
- Faster detection engineering
- SIEM portability

---

## Practical Exercise

### PowerShell Detection

- Generated Sigma rule for encoded PowerShell.
- Mapped to T1059.001.
- Added exclusions for legitimate administrative scripts.

### Windows Event ID 4625

- Created brute-force detection rule.
- Recommended threshold-based correlation.
- Excluded trusted service accounts.

### Registry Persistence

- Detected Run/RunOnce Registry modifications.
- Mapped to T1547.001.
- Reduced false positives using installer exclusions.

### DNS Beaconing

- Generated DNS detection rule.
- Recommended threat intelligence enrichment.
- Highlighted need for SIEM correlation.

---

## Investigation Scenario

AI generated Sigma rules covering:

- Failed authentication
- Encoded PowerShell
- Registry persistence
- DNS beaconing

### MITRE ATT&CK Mapping

- T1110 – Brute Force
- T1059.001 – PowerShell
- T1547.001 – Registry Run Keys
- T1071.004 – DNS

Assessment:

Behavioral correlation and detection tuning significantly improve detection fidelity before production deployment.

---

## Key Takeaways

- Sigma standardizes detection engineering.
- Detection logic should include investigation context.
- False-positive reduction is essential.
- MITRE ATT&CK mapping strengthens detections.
- Always validate and test rules before deployment.

---

## Skills Practiced

- Detection engineering
- Sigma rule writing
- MITRE ATT&CK mapping
- False-positive reduction
- SIEM detection design

---

## Tools Used

- ChatGPT
- Sigma
- Windows Event Logs
- Sysmon

---

## Outcome

Successfully designed Sigma detection rules for multiple attack techniques while understanding the importance of validation, tuning, and behavioral correlation.
