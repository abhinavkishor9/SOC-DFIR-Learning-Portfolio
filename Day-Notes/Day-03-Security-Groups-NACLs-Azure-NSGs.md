# Day 03 – Security Groups, Network ACLs & Azure NSGs

## Overview

Cloud environments rely on network security controls to regulate inbound and outbound traffic. Amazon Web Services (AWS) and Microsoft Azure provide firewall mechanisms that help protect cloud resources from unauthorized access while allowing legitimate communication.

This session focused on understanding the differences between AWS Security Groups, Network Access Control Lists (NACLs), and Azure Network Security Groups (NSGs), along with their role in securing cloud infrastructure.

---

# Concepts Covered

## AWS Security Groups

A Security Group acts as a virtual firewall attached to an EC2 instance.

Key characteristics:

- Operates at the instance level
- Stateful firewall
- Supports allow rules only
- Automatically allows return traffic

Security Groups are commonly used to control access to virtual machines by allowing only specific ports and IP addresses.

---

## Network Access Control Lists (NACLs)

Network ACLs provide an additional layer of security at the subnet level.

Key characteristics:

- Operates at the subnet level
- Stateless firewall
- Supports both allow and deny rules
- Rules are evaluated in numerical order
- First matching rule is applied

Unlike Security Groups, return traffic must be explicitly allowed.

---

## Azure Network Security Groups (NSGs)

Azure NSGs function similarly to AWS Security Groups.

They are used to:

- Filter inbound traffic
- Filter outbound traffic
- Protect Azure Virtual Machines
- Secure Azure Virtual Networks

Azure NSGs are stateful firewalls that support security rules based on source, destination, protocol, and port.

---

# Security Group vs Network ACL

| Security Group | Network ACL |
|---------------|-------------|
| Instance Level | Subnet Level |
| Stateful | Stateless |
| Allow Rules Only | Allow & Deny Rules |
| Automatically allows return traffic | Return traffic must be explicitly allowed |

---

# Lab Observation

During the AWS lab, the default Network ACL associated with the public subnet was reviewed.

Observations included:

- Rule 100 allowed all inbound traffic.
- Rule 100 allowed all outbound traffic.
- Default deny rules existed after Rule 100.
- AWS evaluated rules from the lowest rule number to the highest.
- The first matching rule determined whether traffic was allowed or denied.

This demonstrated how AWS processes Network ACL rules during packet filtering.

---

# Common Security Risks

Misconfigured network security controls can expose cloud resources to attackers.

Common examples include:

- SSH (Port 22) exposed to the Internet
- RDP (Port 3389) exposed publicly
- Security Groups allowing unrestricted inbound traffic
- Network ACLs configured with overly permissive rules
- Unnecessary open ports

---

# SOC Analyst Perspective

Network security changes are frequently investigated during cloud security incidents.

SOC analysts monitor:

- Security Group modifications
- Network ACL changes
- Newly opened ports
- Public SSH/RDP exposure
- CloudTrail events related to VPC configuration changes

These activities may indicate privilege abuse, misconfiguration, or attacker persistence.

---

# Investigation Workflow

```text
Cloud Resource Created
          ↓
Security Group Applied
          ↓
Network ACL Evaluated
          ↓
Traffic Allowed / Denied
          ↓
CloudTrail Logs Generated
          ↓
SOC Investigation
```

---

# Summary

This session introduced cloud network security controls used to protect AWS and Azure environments. Understanding the differences between Security Groups, Network ACLs, and Azure NSGs enables SOC analysts to investigate unauthorized network exposure, identify configuration weaknesses, and monitor cloud infrastructure for suspicious changes.
