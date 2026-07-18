# Day 01 – Cloud Security: AWS & Azure Basics

## Overview

Cloud computing enables organizations to access computing resources such as servers, storage, databases, networking, and software over the Internet without maintaining physical infrastructure. Cloud providers deliver these services on demand using a pay-as-you-go pricing model, allowing businesses to scale resources efficiently while reducing operational costs.

For SOC analysts, understanding cloud fundamentals is essential because modern organizations increasingly host applications and infrastructure on cloud platforms such as Amazon Web Services (AWS) and Microsoft Azure.

---

# Concepts Covered

## Cloud Deployment Models

Cloud environments are generally deployed using one of the following models:

| Model | Description |
|--------|-------------|
| **Public Cloud** | Infrastructure shared among multiple customers and managed by cloud providers. |
| **Private Cloud** | Dedicated cloud environment used exclusively by a single organization. |
| **Hybrid Cloud** | Combination of public and private cloud environments for greater flexibility and security. |

---

## Cloud Service Models

Cloud providers offer services at different management levels.

| Model | Description | Examples |
|--------|-------------|----------|
| **IaaS** | Provides virtual infrastructure such as servers, storage, and networking. | AWS EC2, Azure Virtual Machines |
| **PaaS** | Provides a platform for application development without managing infrastructure. | AWS Elastic Beanstalk, Azure App Service |
| **SaaS** | Delivers complete software applications over the Internet. | Microsoft 365, Gmail, Salesforce |

---

## Shared Responsibility Model

One of the most important cloud security principles is the Shared Responsibility Model.

### Cloud Provider Responsibilities

- Physical data centers
- Hardware
- Networking
- Hypervisor
- Cloud infrastructure

### Customer Responsibilities

- User identities
- IAM permissions
- Applications
- Data
- Encryption
- Security configurations

**Key Principle**

> Cloud providers secure **the cloud**, while customers secure **everything deployed within the cloud**.

---

# Core Cloud Services

## Amazon Web Services (AWS)

- EC2 – Virtual Machines
- S3 – Object Storage
- IAM – Identity & Access Management
- VPC – Virtual Private Cloud
- CloudTrail – API Audit Logging
- CloudWatch – Monitoring & Alerts

## Microsoft Azure

- Azure Virtual Machines
- Azure Blob Storage
- Microsoft Entra ID
- Azure Virtual Network
- Azure Monitor
- Azure Activity Logs

---

# Common Cloud Security Risks

SOC analysts frequently investigate security incidents caused by cloud misconfigurations rather than vulnerabilities in the cloud platform itself.

Common risks include:

- Misconfigured storage buckets
- Weak IAM permissions
- Credential theft
- Excessive privileges
- Publicly exposed services
- Data exfiltration
- Insecure APIs

---

# SOC Analyst Perspective

Cloud environments generate valuable security telemetry that enables analysts to detect and investigate suspicious activity.

Typical investigation scenarios include:

- Suspicious cloud logins
- IAM privilege escalation
- Unauthorized API calls
- Public storage exposure
- Configuration changes
- Cloud audit log analysis

---

# AWS vs Azure Service Mapping

| AWS | Microsoft Azure |
|------|-----------------|
| EC2 | Azure Virtual Machines |
| S3 | Azure Blob Storage |
| IAM | Microsoft Entra ID |
| VPC | Azure Virtual Network |
| CloudTrail | Azure Activity Logs |
| CloudWatch | Azure Monitor |

---

# Summary

This session introduced the foundations of cloud computing and the security concepts required for SOC operations. Understanding cloud deployment models, service models, shared responsibility, and core AWS and Azure services provides the basis for investigating cloud-based security incidents and monitoring cloud environments effectively.
