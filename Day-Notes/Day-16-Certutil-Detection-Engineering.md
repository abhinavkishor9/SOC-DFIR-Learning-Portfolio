# Day 16 – Certutil Detection Engineering

## Overview

Certutil is a legitimate Microsoft utility used for certificate management and file encoding. Because it is a trusted Windows binary, attackers frequently abuse it as a Living-off-the-Land Binary (LOLBin). This lab focused on detecting malicious Certutil usage while minimizing false positives.

---

## Learning Objectives

- Understand legitimate Certutil usage.
- Identify attacker abuse techniques.
- Design high-fidelity detections.
- Apply detection tuning.
- Correlate endpoint events.

---

## Key Concepts

### Legitimate Uses

- Certificate management
- File hashing
- Certificate validation
- Base64 encoding/decoding

### Common Attacker Abuse

- Payload download (-urlcache)
- Base64 decoding (-decode)
- Base64 encoding (-encode)
- LOLBin abuse

### Detection Opportunities

- Suspicious command-line arguments
- Network communication
- Suspicious parent processes
- User-writable directories

---

## Practical Exercise

Designed detections for:

- Payload downloads
- Base64 encoding
- Base64 decoding
- Suspicious parent processes
- External network communication

Improved detection quality by:

- Filtering command-line arguments
- Allowlisting trusted PKI infrastructure
- Monitoring AppData and Downloads
- Correlating multiple events

---

## Investigation Scenario

Observed attack chain:

Certutil Download
↓
Payload Saved
↓
Encoded PowerShell
↓
HTTPS Connection
↓
Registry Persistence

### MITRE ATT&CK

- T1218 – System Binary Proxy Execution
- T1105 – Ingress Tool Transfer
- T1059.001 – PowerShell
- T1027 – Obfuscated Files
- T1071.001 – Web Protocols
- T1547.001 – Registry Run Keys

Severity: **Critical**

---

## Key Takeaways

- Certutil is frequently abused as a LOLBin.
- Behavior-based detections outperform process-name detections.
- Event correlation improves confidence.
- Detection tuning greatly reduces false positives.

---

## Skills Practiced

- Detection engineering
- LOLBin detection
- Endpoint analysis
- Event correlation
- Detection tuning

---

## Tools Used

- Sysmon
- Windows Event Logs
- ChatGPT

---

## Outcome

Built high-quality detections for Certutil abuse using behavioral indicators and multi-event correlation.
