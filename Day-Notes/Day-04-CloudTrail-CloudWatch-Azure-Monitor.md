# Day 04 – Cloud Logs: CloudTrail, CloudWatch, Azure Activity Logs & Azure Monitor

## Overview

Effective cloud security relies on continuous monitoring and audit logging. AWS and Microsoft Azure provide native services that record administrative activities, monitor resource health, and generate alerts for suspicious behavior.

This session explored the differences between logging and monitoring services and demonstrated how SOC analysts use cloud logs during investigations.

---

# Concepts Covered

## AWS CloudTrail

AWS CloudTrail is the primary audit logging service within AWS.

It records API calls and administrative activities performed across AWS resources.

Common events include:

- ConsoleLogin
- CreateUser
- CreateAccessKey
- RunInstances
- AuthorizeSecurityGroupIngress

CloudTrail enables analysts to determine:

- Who performed an action
- When it occurred
- Which resource was affected
- Whether the action succeeded

---

## AWS CloudWatch

CloudWatch is AWS's monitoring platform.

It collects operational metrics such as:

- CPU utilization
- Network traffic
- Disk activity
- Application performance
- Resource health

CloudWatch also generates alerts when predefined thresholds are exceeded.

---

## Azure Activity Logs

Azure Activity Logs perform a similar role to AWS CloudTrail.

They record:

- Administrative actions
- Resource modifications
- Subscription-level events

These logs provide an audit trail for Azure environments.

---

## Azure Monitor

Azure Monitor provides performance monitoring and health metrics for Azure resources.

It supports:

- Performance monitoring
- Resource health
- Metrics collection
- Alert generation

Azure Monitor is conceptually similar to AWS CloudWatch.

---

# Lab Observation

The AWS Skill Builder environment was used to explore CloudTrail.

During the investigation:

- Authentication succeeded successfully.
- Attempts to view CloudTrail Trails were denied.
- The AWSLabsUser role lacked sufficient permissions.
- AWS returned an **AccessDenied** error caused by IAM restrictions.

Although access was denied, the exercise demonstrated how IAM policies enforce authorization within AWS environments.

---

# Authentication vs Authorization

A key concept learned during the lab was the difference between authentication and authorization.

| Authentication | Authorization |
|---------------|---------------|
| Verifies identity | Determines permissions |
| Confirms who the user is | Determines what the user can access |

The AWSLabsUser account authenticated successfully but was not authorized to perform the requested CloudTrail action.

---

# SOC Analyst Perspective

Cloud logging services provide valuable evidence during investigations.

Common use cases include:

- Investigating suspicious cloud logins
- Reviewing IAM changes
- Auditing resource modifications
- Identifying failed administrative actions
- Monitoring unusual API activity

AccessDenied events are especially valuable because they indicate attempted actions that were prevented by security controls.

---

# Investigation Workflow

```text
User Action
      ↓
AWS API Call
      ↓
IAM Policy Evaluation
      ↓
CloudTrail Log Generated
      ↓
SOC Investigation
```

---

# Logging vs Monitoring

| Logging | Monitoring |
|----------|------------|
| Records historical events | Tracks system health in real time |
| Supports investigations | Supports operational awareness |
| CloudTrail | CloudWatch |
| Azure Activity Logs | Azure Monitor |

---

# Summary

CloudTrail and Azure Activity Logs provide audit records of administrative activity, while CloudWatch and Azure Monitor focus on performance monitoring and alerting. Understanding the distinction between logging and monitoring enables SOC analysts to investigate cloud incidents, validate administrative actions, and identify suspicious activity using cloud-native security services.
