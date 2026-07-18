# Day 06 – AWS Defender Tools & Access Control Investigation

## Overview

AWS provides several native security services that help organizations monitor cloud environments, detect threats, identify vulnerabilities, and investigate suspicious activity. These services generate valuable telemetry that enables SOC analysts to perform cloud-based investigations.

This session introduced AWS security tools and examined how organizational security controls such as Service Control Policies (SCPs) can restrict access to security information.

---

# Concepts Covered

## AWS CloudTrail

CloudTrail records AWS API activity and administrative actions.

It enables investigators to determine:

- Who performed an action
- When it occurred
- Which resource was affected
- Whether the action succeeded

CloudTrail serves as the primary audit log during cloud investigations.

---

## Amazon GuardDuty

GuardDuty continuously analyzes AWS activity to detect suspicious behavior.

It uses data from:

- CloudTrail
- DNS Logs
- VPC Flow Logs

Common detections include:

- Credential compromise
- Cryptocurrency mining
- Unauthorized API calls
- Reconnaissance activity

---

## AWS Security Hub

Security Hub provides a centralized dashboard for AWS security findings.

It aggregates alerts from multiple AWS security services, allowing analysts to review security posture from a single location.

---

## Amazon Inspector

Inspector automatically scans AWS resources for:

- Vulnerabilities
- Missing patches
- Configuration weaknesses
- Security best practice violations

---

## IAM Access Analyzer

IAM Access Analyzer identifies:

- Excessive permissions
- External resource sharing
- Unintended trust relationships
- Public resource exposure

---

## Amazon Macie

Macie helps identify and classify sensitive information stored in Amazon S3.

It is commonly used for:

- Data discovery
- Personally Identifiable Information (PII) detection
- Compliance monitoring

---

# Investigation Scenario

A cloud security analyst attempted to review CloudTrail Event History and other AWS security services within a training environment.

Although authentication was successful, multiple actions were blocked due to organization-wide security restrictions. The objective was to determine why access was denied and understand the impact on cloud investigations.

---

# Lab Findings

Environment:

- AWS Skill Builder Sandbox
- Region: us-west-2
- Role: AWSLabsUser

Observations:

- IAM Access Analyzer opened successfully.
- GuardDuty displayed permission warnings.
- CloudTrail Event History could not be accessed.
- AWS returned an **AccessDeniedException** for `cloudtrail:LookupEvents`.

The investigation confirmed that access restrictions originated from an AWS Organizations **Service Control Policy (SCP)** rather than the IAM role itself.

---

# Understanding Service Control Policies (SCPs)

AWS evaluates permissions using multiple layers:

```text
Service Control Policy (SCP)
          ↓
IAM Policies
          ↓
Resource Policies
          ↓
Final Access Decision
```

An **Explicit Deny** within an SCP overrides every Allow permission granted through IAM policies.

---

# SOC Analyst Perspective

When investigating AccessDenied events, analysts should determine:

- Which action was blocked?
- Which policy caused the restriction?
- Was the activity expected?
- Did the restriction originate from IAM, a resource policy, or an SCP?

Understanding permission evaluation is essential because restricted visibility can directly impact cloud investigations.

---

# Investigation Workflow

```text
User Performs Action
          ↓
AWS Authorization Process
          ↓
SCP Evaluation
          ↓
IAM Policy Evaluation
          ↓
Access Granted / Access Denied
          ↓
Cloud Investigation
```

---

# Summary

This session introduced AWS-native security services and demonstrated how layered access controls protect cloud environments. Understanding CloudTrail, GuardDuty, Security Hub, Inspector, IAM Access Analyzer, Macie, and Service Control Policies enables SOC analysts to investigate cloud incidents while recognizing how organizational security controls affect investigative visibility.
