# Day 27 – Windows Authentication & RDP Investigation (Wazuh)

## Objective

Investigate Windows authentication events collected by Wazuh to understand how SOC analysts validate successful and failed logons, identify potential unauthorized access, and distinguish normal authentication activity from malicious behavior using Windows Security Logs and the Wazuh Threat Hunting Dashboard.

---

## Windows Authentication Fundamentals

Windows records every authentication attempt in the **Security Log**, making authentication events one of the primary data sources during incident investigations.

Common authentication events include:

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

Important fields available during analysis include:

- Username
- Computer Name
- Logon Type
- Timestamp
- Authentication Status
- Workstation Name
- Account Domain

Authentication events alone do not confirm an attack. Analysts must correlate authentication activity with endpoint telemetry such as process creation, PowerShell execution, registry changes, and network connections before determining malicious activity.

---

## Authentication Investigation Workflow
