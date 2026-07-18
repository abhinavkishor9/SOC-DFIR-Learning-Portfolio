# Day 7 – AWS Cloud Security Access Control Investigation

## Objective

Investigate AWS security service access restrictions within an AWS Skill Builder sandbox and determine whether permission errors indicate a security incident or correctly enforced cloud security controls.

---

## Investigation Scenario

A cloud administrator reports that multiple AWS security services cannot be accessed.

As the SOC Analyst, the objective is to determine whether the issue is caused by:

- AWS service failures
- Unauthorized activity
- Misconfiguration
- Correctly enforced security controls

---

## Services Investigated

- AWS CloudTrail
- Amazon GuardDuty
- AWS Security Hub
- Amazon Inspector
- Amazon Macie
- IAM Access Analyzer
- Amazon S3 Security Controls
- AWS Security Groups

---

## Investigation Workflow

1. Review CloudTrail event history.
2. Validate GuardDuty access.
3. Check Security Hub status.
4. Review Amazon Inspector permissions.
5. Investigate Amazon Macie access.
6. Verify IAM Access Analyzer.
7. Review Amazon S3 security controls.
8. Examine Security Group configuration.
9. Correlate permission errors across services.
10. Determine the root cause.

---

## Investigation Findings

| Service | Observation |
|----------|-------------|
| CloudTrail | Access blocked by Service Control Policy (SCP) |
| GuardDuty | Permission restricted |
| Security Hub | Access denied due to IAM restrictions |
| Amazon Inspector | Activation restricted |
| Amazon Macie | Explicit IAM deny observed |
| IAM Access Analyzer | Access unavailable |
| Amazon S3 | Security settings protected by IAM permissions |
| Security Groups | Intentionally permissive for training environment |

---

## Root Cause Analysis

The investigation confirmed that all observed permission errors resulted from intentionally enforced AWS security controls rather than malicious activity.

Security mechanisms identified included:

- Least-Privilege IAM
- Service Control Policies (SCPs)
- Identity-Based IAM Policies
- AWS Skill Builder sandbox restrictions

---

## Investigation Outcome

**Incident Severity:** Informational

**Status:** Closed – No Security Incident

No indicators of compromise were identified. The AWS environment functioned as designed, with security controls preventing unauthorized access to cloud security services.

---

## Skills Demonstrated

- AWS Cloud Security Investigation
- Identity and Access Management (IAM)
- Service Control Policies (SCPs)
- AWS Security Services
- Amazon S3 Security Assessment
- Security Validation
- Root Cause Analysis
- SOC Investigation Methodology
- Cloud Access Control Analysis
- Security Documentation

---

## Key Takeaway

Permission errors do not always indicate security incidents. Effective SOC analysts validate whether access restrictions are caused by malicious activity or by correctly implemented cloud security controls such as IAM policies, Service Control Policies (SCPs), and least-privilege access.
