# Day 22 – Wazuh Manager & Agent

## Overview

The Wazuh Agent and Wazuh Manager form the foundation of the Wazuh SIEM platform. The Agent collects endpoint telemetry, while the Manager analyzes events, applies detection rules, correlates activity, and generates security alerts for investigation.

---

## Learning Objectives

- Understand the roles of the Wazuh Agent and Manager.
- Learn how events flow through the Wazuh platform.
- Understand Agent registration.
- Verify Agent communication.
- Troubleshoot common connectivity issues.

---

## Key Concepts

### Wazuh Agent

The Agent is installed on monitored endpoints and is responsible for collecting:

- Windows Event Logs
- Sysmon Events
- File Integrity Monitoring (FIM)
- Registry Changes
- Process Creation
- System Inventory

The Agent **collects data only** and does not generate alerts.

### Wazuh Manager

The Manager receives events from Agents and performs:

- Log decoding
- Rule matching
- Event correlation
- Severity assignment
- Alert generation

### Event Processing Workflow

Endpoint Activity

↓

Wazuh Agent

↓

TCP 1514

↓

Wazuh Manager

↓

Detection Rules

↓

Wazuh Indexer

↓

Dashboard

---

## Practical Exercise

Studied:

- Agent installation
- Manager communication
- Agent registration
- Secure key exchange
- Alert generation workflow

Verified:

- Active Agent status
- Heartbeat
- Log collection
- Dashboard visibility

---

## Investigation Scenario

Observed attack sequence:

- Failed logins
- Successful RDP login
- Encoded PowerShell
- Certutil download
- Registry persistence
- Scheduled Task creation
- HTTPS communication

The Agent collected endpoint telemetry while the Manager correlated events into a high-severity alert.

---

## Key Takeaways

- Agents collect endpoint telemetry.
- Managers analyze and correlate events.
- Agent registration occurs over TCP 1515.
- Log forwarding uses TCP 1514.
- Healthy Agent communication is essential for detection.

---

## Skills Practiced

- Wazuh architecture
- Agent management
- Event collection
- Troubleshooting
- SIEM monitoring

---

## Tools Used

- Wazuh Agent
- Wazuh Manager
- Wazuh Dashboard

---

## Outcome

Developed an understanding of how Wazuh Agents and Managers work together to transform endpoint telemetry into actionable security alerts.
