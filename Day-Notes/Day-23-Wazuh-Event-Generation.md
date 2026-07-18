# Day 23 – Wazuh Event Generation

## Overview

Security events are the foundation of every SIEM investigation. This lab focused on understanding how Windows and Sysmon events are generated, collected by Wazuh, processed by the Manager, and converted into security alerts.

---

## Learning Objectives

- Understand security events.
- Differentiate events from alerts.
- Learn Windows event sources.
- Follow the event lifecycle.
- Verify event collection.

---

## Key Concepts

### Event vs Alert

| Event | Alert |
|--------|-------|
| Records system activity | Generated when detection rules match |
| Created by Windows or Sysmon | Created by Wazuh Manager |

### Common Event Sources

- Windows Security Logs
- System Logs
- Application Logs
- Sysmon
- PowerShell Logs

### Event Lifecycle

User Activity

↓

Windows Event

↓

Windows Event Log / Sysmon

↓

Wazuh Agent

↓

Wazuh Manager

↓

Detection Rules

↓

Alert

↓

Dashboard

---

## Practical Exercise

Generated events for:

- Failed login
- Successful login
- PowerShell execution
- Certutil execution
- Registry modification
- Scheduled Task creation

Verified that events reached the Wazuh Dashboard.

---

## Investigation Scenario

Observed timeline:

- Multiple failed logins
- Successful login
- PowerShell execution
- Certutil execution
- Registry persistence
- Scheduled Task creation

Although individual events appeared legitimate, their correlation suggested a possible compromise.

---

## Key Takeaways

- Events are the foundation of investigations.
- Not every event generates an alert.
- Sysmon provides valuable endpoint telemetry.
- Event correlation improves investigation quality.
- Verification confirms successful log collection.

---

## Skills Practiced

- Event generation
- Log verification
- Event correlation
- Wazuh monitoring
- Threat analysis

---

## Tools Used

- Windows Event Viewer
- Sysmon
- Wazuh Dashboard

---

## Outcome

Learned how endpoint activity becomes actionable security alerts through Wazuh's event processing pipeline.
