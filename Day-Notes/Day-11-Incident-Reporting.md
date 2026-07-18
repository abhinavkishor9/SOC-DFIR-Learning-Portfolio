# Day 11 – Incident Reporting

## Overview

Incident reporting is a critical SOC responsibility that documents the details of a security incident, investigation findings, evidence, impact, response actions, and recommendations. A well-written incident report enables effective communication between SOC analysts, incident responders, management, and other stakeholders.

---

## Learning Objectives

- Understand the structure of an incident report.
- Learn how to summarize security investigations.
- Document Indicators of Compromise (IoCs).
- Map incidents to MITRE ATT&CK.
- Differentiate confirmed evidence from assumptions.

---

## Key Concepts

### Core Components of an Incident Report

- Executive Summary
- Detection Summary
- Investigation Findings
- Indicators of Compromise (IoCs)
- MITRE ATT&CK Mapping
- Severity Assessment
- Containment Actions
- Recommendations

### Characteristics of a Good Incident Report

- Accurate
- Evidence-based
- Clear and concise
- Actionable
- Easy to understand

---

## Practical Exercise

AI assisted in generating incident reports for multiple investigation scenarios.

### Windows Authentication Investigation

- Summarized failed and successful logins.
- Extracted usernames and source information.
- Suggested account validation.

### Sysmon Investigation

- Documented encoded PowerShell execution.
- Identified external network communication.
- Recommended endpoint isolation.

### AWS CloudTrail Investigation

- Reported IAM policy modifications.
- Highlighted possible privilege escalation.
- Recommended authorization verification.

### Multi-Source Investigation

AI correlated Windows, Sysmon, Firewall, and CloudTrail telemetry into a unified incident report.

---

## Investigation Scenario

Correlated evidence indicated:

- Authentication anomalies
- Encoded PowerShell execution
- Outbound network communication
- IAM privilege modification

### MITRE ATT&CK Mapping

- T1110 – Brute Force
- T1078 – Valid Accounts
- T1059.001 – PowerShell
- T1027 – Obfuscated Files or Information
- T1071.001 – Application Layer Protocol
- T1098 / T1098.003 – Account Manipulation

Severity Assessment: **Critical**

---

## Key Takeaways

- Incident reports should rely on confirmed evidence.
- Clearly separate observations from assumptions.
- MITRE ATT&ATT&CK mapping improves documentation.
- AI accelerates report creation but requires analyst review.
- Good documentation improves future investigations.

---

## Skills Practiced

- Incident documentation
- Evidence summarization
- IoC documentation
- MITRE ATT&CK mapping
- Report writing

---

## Tools Used

- ChatGPT
- Windows Event Logs
- Sysmon
- AWS CloudTrail

---

## Outcome

Successfully created structured incident reports by correlating evidence from multiple log sources while maintaining clear documentation and investigation methodology.
