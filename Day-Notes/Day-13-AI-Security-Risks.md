# Day 13 – AI Security Risks

## Overview

Artificial Intelligence improves SOC efficiency by assisting with log analysis, threat detection, and incident reporting. However, improper use of AI introduces risks such as prompt injection, sensitive data exposure, hallucinations, and misuse. SOC analysts must understand these risks and apply responsible AI practices.

---

## Learning Objectives

- Understand common AI security risks.
- Learn secure AI usage practices.
- Recognize AI limitations.
- Protect sensitive organizational data.
- Appreciate the importance of human validation.

---

## Key Concepts

### Common AI Security Risks

#### Prompt Injection

Malicious prompts attempt to manipulate AI into ignoring instructions or revealing unauthorized information.

#### Sensitive Data Exposure

Uploading confidential logs, credentials, API keys, or internal infrastructure details to public AI platforms.

#### AI Hallucination

AI generating incorrect or unsupported conclusions because of incomplete context.

#### Model Abuse

Using AI to assist phishing, malware development, reconnaissance, or bypassing security controls.

### Responsible AI Usage

- Protect sensitive information.
- Use approved enterprise AI platforms.
- Validate AI-generated output.
- Maintain audit logs.
- Keep humans responsible for security decisions.

---

## Practical Exercise

### Prompt Injection

Studied how malicious prompts influence AI behavior.

Recommended:

- Prompt isolation
- Input validation
- Human review

### AI Hallucination

Observed how incomplete evidence can produce unsupported conclusions.

Emphasized:

- Evidence validation
- Additional telemetry collection

### Sensitive Data Protection

Identified risks of exposing:

- API keys
- Internal IP addresses
- Usernames
- Infrastructure information

Recommended:

- Data sanitization
- DLP controls
- Credential rotation
- Enterprise AI platforms

---

## Investigation Scenario

An employee uploaded internal security logs containing:

- Internal usernames
- Internal IP addresses
- Active API key

AI assessed:

- Sensitive data exposure
- Potential credential compromise
- Compliance concerns

Recommended:

- Immediate API key rotation
- Exposure assessment
- Audit log review
- Stronger AI governance controls

Severity Assessment: **High**

---

## Key Takeaways

- AI should support—not replace—analyst decision making.
- Never upload sensitive data to unapproved AI platforms.
- Validate every AI-generated conclusion.
- Human oversight remains essential.
- Responsible AI practices reduce organizational risk.

---

## Skills Practiced

- AI risk assessment
- Secure AI usage
- Data protection awareness
- AI governance
- Investigation validation

---

## Tools Used

- ChatGPT

---

## Outcome

Developed an understanding of AI-related security risks and learned best practices for using AI responsibly within SOC operations while protecting sensitive organizational information.
