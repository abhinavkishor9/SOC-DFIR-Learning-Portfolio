# Day 26 – Wazuh Windows Authentication & RDP Log Investigation

## Objective

Investigate Windows authentication events and Remote Desktop Protocol (RDP) logons using Wazuh Threat Hunting, correlate related endpoint activity, and determine whether authentication represents legitimate administration or unauthorized access.

---

## Topics Covered

- Windows Authentication Events
- Event IDs 4624 & 4625
- Logon Type 10
- RDP Investigation
- Authentication Correlation
- Threat Hunting Dashboard
- Incident Response Playbook
- MITRE ATT&CK Mapping

---

## Windows Authentication Events

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| Logon Type 10 | Remote Desktop Logon |

---

## Investigation Fields

Review:

- Username
- Computer Name
- Timestamp
- Logon Type
- Authentication Status
- Source IP (if available)

---

## Authentication Workflow

```text
Windows Authentication
        │
        ▼
Windows Security Log
        │
        ▼
Event ID 4624 / 4625
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

## Investigation Scenario

Observed timeline:

| Time | Activity |
|------|----------|
| 09:30 | Four failed logons (4625) |
| 09:32 | Successful logon (4624) |
| 09:32 | Logon Type 10 (RDP) |
| 09:34 | PowerShell execution |
| 09:36 | Outbound HTTPS connection |

The analyst observed multiple failed authentication attempts followed by a successful RDP session. Endpoint activity immediately after authentication increased suspicion of unauthorized access.

---

## MITRE ATT&CK Mapping

| Activity | Technique |
|----------|-----------|
| Failed Logons | T1110 – Brute Force |
| RDP Login | T1021.001 – Remote Desktop Protocol |
| PowerShell | T1059.001 – PowerShell |

---

## Incident Response Playbook

### Trigger Conditions

- Multiple failed logons
- Successful login after repeated failures
- Unusual login time
- Remote Desktop logon (Type 10)
- Authentication alerts from Wazuh

---

### Phase 1 – Identification

Collect:

- Event ID
- Username
- Computer Name
- Logon Type
- Timestamp

---

### Phase 2 – Investigation

Verify:

- Authentication history
- Failed login count
- Login timing
- Source IP
- Correlated PowerShell or Sysmon activity
- User authorization

---

### Phase 3 – Containment

If malicious:

- Isolate endpoint
- Disable compromised account
- Block malicious IP
- Preserve forensic evidence

---

### Phase 4 – Eradication

- Remove persistence
- Delete malicious Scheduled Tasks
- Scan for malware
- Reset credentials

---

### Phase 5 – Recovery

- Restore endpoint
- Monitor authentication
- Verify no recurring suspicious activity

---

### Phase 6 – Lessons Learned

Document:

- Root cause
- Timeline
- IOCs
- Response actions
- Detection improvements
- Recommendations

---

## Investigation Workflow

```text
Authentication Alert
        │
        ▼
Validate Alert
        │
        ▼
Collect Evidence
        │
        ▼
Correlate Events
        │
        ▼
Assess Severity
        │
        ▼
Contain
        │
        ▼
Eradicate
        │
        ▼
Recover
        │
        ▼
Lessons Learned
```

---

## Analyst Checklist

- Validate alert
- Verify Event IDs 4624 / 4625
- Identify affected account
- Review Logon Type
- Correlate endpoint activity
- Assess severity
- Contain if malicious
- Document findings
- Recommend detection improvements

---

## Skills Demonstrated

- Windows Authentication Analysis
- RDP Investigation
- Event Correlation
- Wazuh Threat Hunting
- Incident Response
- MITRE ATT&CK Mapping

---

## Key Takeaway

Authentication events should never be investigated in isolation. Correlating failed logons, successful RDP sessions, PowerShell execution, and network activity provides stronger evidence of compromise and enables more accurate incident response.
