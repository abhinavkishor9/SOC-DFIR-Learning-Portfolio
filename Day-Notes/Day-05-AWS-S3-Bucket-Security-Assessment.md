# Day 05 – AWS S3 Bucket Security Assessment

## Overview

Amazon Simple Storage Service (Amazon S3) is AWS's object storage service used to store files, backups, logs, application data, and static website content. Since S3 buckets often contain sensitive information, securing them is a critical responsibility for cloud security teams.

This session focused on assessing S3 bucket security configurations, understanding how IAM permissions affect visibility, and analyzing the impact of restricted access during cloud security investigations.

---

# Concepts Covered

## Amazon S3

Amazon S3 stores objects inside logical containers known as buckets. Organizations commonly use S3 for:

- Application data
- Backups
- Log storage
- Static website hosting
- Data archival

Proper access control is essential because misconfigured buckets can expose sensitive information publicly.

---

## IAM Permissions

Identity and Access Management (IAM) determines which actions users or roles can perform against AWS resources.

Examples include:

- ListBucket
- GetBucketPolicy
- GetBucketLogging
- GetBucketVersioning
- GetEncryptionConfiguration

Without appropriate IAM permissions, security analysts cannot fully assess bucket configurations.

---

## Explicit Deny

AWS follows a strict permission evaluation process.

An **Explicit Deny** always overrides any Allow permission granted through IAM policies.

This principle ensures that sensitive resources remain protected even when broader permissions exist elsewhere.

---

# Security Controls Reviewed

During the assessment, several important S3 security controls were examined:

- Bucket Policy
- Block Public Access
- Bucket Versioning
- Default Encryption
- Server Access Logging

These controls help protect stored data from unauthorized access and improve auditing capabilities.

---

# Investigation Scenario

A cloud security analyst was assigned to verify whether an Amazon S3 bucket was securely configured.

During the assessment, multiple configuration settings could not be viewed because the AWSLabsUser role lacked sufficient permissions. The objective was to determine whether the restrictions were caused by IAM policies or resource-based security controls and document the investigation findings.

---

# Lab Findings

The following observations were made during the investigation:

| Security Control | Observation |
|------------------|-------------|
| Object Listing | Access Denied |
| Bucket Policy | Access Denied |
| Public Access Block | Explicit Deny |
| Bucket Versioning | Access Denied |
| Default Encryption | Access Denied |
| Server Access Logging | Access Denied |

Evidence showed that the AWSLabsUser role could authenticate successfully but lacked authorization to retrieve bucket configuration details.

---

# Security Impact

Limited visibility into bucket configurations prevents analysts from verifying critical security controls such as:

- Public exposure
- Encryption status
- Logging configuration
- Versioning
- Bucket policies

Without this information, it becomes difficult to assess whether sensitive data is adequately protected.

---

# SOC Analyst Perspective

Cloud storage misconfigurations are among the most common causes of cloud data breaches.

SOC analysts should monitor CloudTrail events related to S3, including:

- GetBucketPolicy
- PutBucketPolicy
- DeleteBucketPolicy
- PutBucketEncryption
- PutBucketLogging
- PutBucketVersioning

Repeated **AccessDenied** events should also be investigated because they may indicate:

- Misconfigured IAM permissions
- Unauthorized enumeration attempts
- Overly restrictive access policies

---

# Investigation Workflow

```text
Access S3 Bucket
        ↓
IAM Permission Evaluation
        ↓
Retrieve Bucket Configuration
        ↓
Access Allowed / Access Denied
        ↓
Review Security Controls
        ↓
Document Findings
```

---

# Summary

This session demonstrated the importance of securing Amazon S3 buckets using appropriate IAM permissions and resource-based policies. The investigation highlighted how restricted permissions affect security assessments and reinforced the role of S3 security controls in protecting cloud data from unauthorized access.
