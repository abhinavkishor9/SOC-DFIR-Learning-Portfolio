# Day 08 – LLM Basics for SOC Analysts

## Overview

Large Language Models (LLMs) are becoming valuable assistants in modern Security Operations Centers (SOCs). They help analysts understand alerts, summarize logs, generate detection rules, explain attack techniques, and accelerate incident reporting. While LLMs significantly improve analyst productivity, they should complement—not replace—human analysis and validation.

This session introduced the fundamentals of LLMs, their core concepts, practical SOC use cases, and the importance of verifying AI-generated outputs against real security evidence.

---

# Concepts Covered

## What is a Large Language Model (LLM)?

A Large Language Model is an artificial intelligence model trained on massive amounts of text to understand and generate human language. Instead of following predefined rules, LLMs predict the next most likely token based on context and learned language patterns.

Unlike traditional software, LLMs generate context-aware responses that can assist analysts with technical explanations, detection engineering, and documentation.

---

## Core Concepts

### Tokens

Tokens are the smallest units of text processed by an LLM. A sentence is broken into multiple tokens before being analyzed.

### Context Window

The context window defines how much information the model can remember within a conversation. A larger context window allows the model to understand longer discussions and maintain continuity.

### Parameters

Parameters are the learned numerical values inside an LLM that represent language patterns and relationships acquired during training.

### Prompt Engineering

Prompt engineering is the practice of writing clear, structured instructions to obtain accurate and relevant responses from an LLM.

### Hallucinations

Hallucinations occur when an LLM generates information that appears convincing but is factually incorrect or unsupported. Analysts must always verify AI-generated outputs using real evidence.

### Retrieval-Augmented Generation (RAG)

RAG combines an LLM with external knowledge sources to improve response accuracy and reduce hallucinations by retrieving relevant information before generating an answer.

---

# Practical Exercise

During the exercises, the LLM was used to:

- Explain ransomware attacks and their lifecycle.
- Summarize Windows Event ID 4625.
- Map attacker activity to the MITRE ATT&CK framework.
- Generate Splunk SPL queries.
- Assist with SOC investigation documentation.

These exercises demonstrated how AI can reduce manual effort while improving the speed of analysis.

---

# Investigation Scenario

A SOC analyst observed multiple Windows Event ID **4625** entries indicating repeated failed logon attempts.

The LLM analyzed the event and suggested:

- Possible brute-force activity.
- Relevant MITRE ATT&CK techniques.
- Additional Windows events to investigate.
- Potential Indicators of Compromise (IOCs).
- Detection recommendations.

The analyst then validated the AI-generated findings using Windows Event Logs, SIEM alerts, endpoint telemetry, and threat intelligence before confirming the incident.

This exercise reinforced that AI assists investigations but does not replace evidence-based analysis.

---

# SOC Analyst Perspective

LLMs can significantly improve daily SOC operations by assisting with:

- Alert triage
- Log summarization
- IOC extraction
- MITRE ATT&CK mapping
- Detection engineering
- Sigma rule generation
- Splunk SPL creation
- Incident report writing
- Technical documentation

However, analysts should always verify AI-generated content before using it in production environments or incident reports.

---

# Best Practices

When using LLMs in cybersecurity:

- Write clear and specific prompts.
- Validate every response using actual logs.
- Cross-check AI findings with SIEM and EDR data.
- Never rely solely on AI for incident decisions.
- Use AI to improve efficiency, not replace analyst judgment.

---

# Summary

This session introduced the role of Large Language Models in Security Operations. By understanding concepts such as tokens, context windows, prompt engineering, hallucinations, and Retrieval-Augmented Generation (RAG), SOC analysts can effectively use AI to accelerate investigations, generate detection logic, and improve documentation while maintaining evidence-based decision-making.
