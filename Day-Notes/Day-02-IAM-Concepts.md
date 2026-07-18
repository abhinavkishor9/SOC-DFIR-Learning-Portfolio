# Day 02 – Identity & Access Management (IAM)

## Overview

Identity and Access Management (IAM) is one of the most important security components in any cloud environment. It controls who can access cloud resources, how users authenticate, and what actions they are authorized to perform.

Proper IAM implementation reduces the risk of unauthorized access, privilege escalation, and credential misuse while supporting the Principle of Least Privilege.

---

# Concepts Covered

## Identity

An identity represents a user, application, or service that interacts with cloud resources.

Examples include:

- Cloud users
- Applications
- Virtual machines
- Service accounts

---

## Authentication

Authentication verifies the identity of a user or system before access is granted.

Common authentication methods include:

- Username & Password
- Multi-Factor Authentication (MFA)
- Access Keys
- Certificates

---

## Authorization

Authorization determines which resources an authenticated identity is allowed to access.

Permissions are typically assigned using policies or role-based access controls.

---

# AWS IAM Components

AWS IAM provides several components used to manage identities and permissions.

| Component | Purpose |
|-----------|---------|
| Users | Individual identities |
| Groups | Collection of users with similar permissions |
| Roles | Temporary permissions assigned to users or services |
| Policies | JSON documents defining allowed actions |

---

# Azure IAM Components

Azure uses Microsoft Entra ID together with Role-Based Access Control (RBAC).

Major components include:

- Users
- Groups
- Roles
- Service Principals

---

# Security Best Practices

Effective IAM management follows several important security principles.

### Principle of Least Privilege

Users should receive only the permissions required to perform their tasks.

### Role-Based Access Control (RBAC)

Permissions should be assigned to roles rather than individual users whenever possible.

### Multi-Factor Authentication

MFA adds an additional layer of protection against credential compromise.

### Avoid Shared Accounts

Individual user accounts improve accountability and auditability.

---

# Common IAM Security Risks

Poor identity management can lead to significant security incidents.

Examples include:

- Excessive permissions
- Weak passwords
- Disabled MFA
- Stale user accounts
- Credential theft

---

# SOC Analyst Perspective

IAM events are frequently investigated within Security Operations Centers because compromised identities often provide attackers with initial access to cloud environments.

Common investigation scenarios include:

- Failed authentication attempts
- Privilege escalation
- MFA modifications
- Creation of new access keys
- Suspicious cloud logins
- Unauthorized role assignments

Analysts correlate IAM events with cloud audit logs to determine whether access attempts are legitimate or malicious.

---

# Investigation Workflow

```text
User Login
      ↓
Authentication
      ↓
Authorization
      ↓
IAM Policies Evaluated
      ↓
Access Granted / Access Denied
      ↓
Cloud Audit Logs Generated
```

---

# Summary

Identity and Access Management forms the foundation of cloud security. Understanding authentication, authorization, users, groups, roles, policies, and RBAC enables SOC analysts to investigate unauthorized access attempts, monitor privileged activity, and detect identity-based attacks effectively.
