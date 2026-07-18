# Day 25 – Wazuh PowerShell Detection

## Objective

Learn how Wazuh monitors PowerShell execution using Sysmon Event ID 1 and understand how SOC analysts distinguish legitimate administrative activity from suspicious PowerShell behavior through event correlation.

---

## Topics Covered

- PowerShell fundamentals
- PowerShell abuse by attackers
- Sysmon Event ID 1 (Process Creation)
- Wazuh PowerShell monitoring
- Command-line analysis
- Threat Hunting Dashboard
- MITRE ATT&CK mapping
- Investigation workflow

---

## Key Concepts

### Why Monitor PowerShell?

PowerShell is a powerful Windows administration and automation tool. Since it is installed by default on Windows systems, attackers frequently abuse it for:

- Malware execution
- Payload downloads
- Defense evasion
- System discovery
- Persistence

PowerShell activity should always be investigated in context rather than treated as malicious by default.

---

## MITRE ATT&CK Mapping

| Tactic | Technique |
|----------|-----------|
| Execution | T1059.001 – PowerShell |

---

## Wazuh Detection Workflow

```text
PowerShell Execution
        │
        ▼
Sysmon Event ID 1
        │
        ▼
Wazuh Agent
        │
        ▼
Wazuh Manager
        │
        ▼
Threat Hunting Dashboard
        │
        ▼
SOC Investigation
```

---

## Important Investigation Fields

During analysis, review:

- Process Image
- Command Line
- User
- Parent Process
- Timestamp

The **Command Line** field provides the highest investigative value.

---

## Lab Activity

Commands executed:

```powershell
Get-Date

Get-Process

powershell.exe -NoProfile Get-Process
```

These generated Sysmon Event ID 1, confirming that:

- Sysmon recorded the process
- Wazuh Agent collected the event
- Wazuh Manager processed the log
- Event appeared in the Threat Hunting Dashboard

---

## Investigation Scenario

Observed sequence:

```text
PowerShell Launch
        │
        ▼
Get-Date
        │
        ▼
Get-Process
        │
        ▼
PowerShell -NoProfile
        │
        ▼
Sysmon Event ID 1
        │
        ▼
Wazuh Collection
```

The analyst verified:

- Image: powershell.exe
- Command Line: powershell.exe -NoProfile Get-Process
- User: Administrator
- Sysmon Event ID 1

Although **-NoProfile** is commonly associated with malicious activity, it is also frequently used by administrators.

---

## Additional Validation

The investigation searched for:

- Encoded PowerShell
- Payload downloads
- Registry persistence
- Scheduled Tasks
- Suspicious child processes
- Outbound network connections

No additional malicious indicators were identified.

---

## Investigation Outcome

The activity was classified as **Legitimate Administrative Testing** because:

- Only trusted PowerShell commands executed
- No encoded commands
- No payload downloads
- No persistence mechanisms
- No suspicious network activity
- Wazuh successfully collected all events

---

## Skills Demonstrated

- Wazuh Threat Hunting
- PowerShell Investigation
- Sysmon Event Analysis
- Process Creation Analysis
- Command-Line Review
- Event Correlation

---

## Key Takeaway

PowerShell execution alone should never be treated as malicious. High-confidence investigations require correlation with registry modifications, persistence mechanisms, network communication, and additional endpoint telemetry before escalating an incident.
