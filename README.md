# TOGAF-Aligned Cloud Security Risk Architecture Framework

## Overview

Cloud security architecture should begin with business risk and security requirements, not with cloud services.

This project demonstrates a structured approach for translating business objectives, regulatory obligations, threat scenarios, and risk tolerance into cloud security architecture decisions. TOGAF concepts provide the architecture lifecycle and governance structure, while security frameworks and threat models provide inputs for determining which controls are appropriate and why.

The objective is to connect:

**Business Requirements → Risk → Threats → Security Controls → Architecture Decisions → Governance and Assurance**

This repository is an architecture and governance project. It does not represent a deployed production environment or claim formal TOGAF, SABSA, NIST, ISO, or CIS certification.

---

## Architecture Problem

Cloud environments often accumulate security controls independently:

- IAM policies are created to solve individual access requirements.
- Network controls are introduced without a documented threat model.
- Logging is enabled without defining what security decisions the telemetry must support.
- Vulnerabilities are prioritized primarily by severity.
- Compliance controls are implemented without connecting them to specific business risks.
- Architecture decisions are made without documenting ownership, exceptions, or residual risk.

The result can be technically sophisticated security without a clear relationship between business requirements, risk, and architectural decisions.

This framework addresses that problem by creating traceability between those layers.

---

## Architecture Principle

> A security control should exist because it addresses an identified business, security, regulatory, or threat requirement—not simply because a cloud platform provides the capability.

The framework therefore treats cloud services as implementation mechanisms rather than the starting point for architecture.

---

## Architecture Decision Flow

The framework uses the following decision sequence:

1. **Identify the business objective**
   - What capability must the organization protect or enable?

2. **Determine security and regulatory requirements**
   - What confidentiality, integrity, availability, privacy, or regulatory obligations apply?

3. **Identify threats and failure scenarios**
   - How could the requirement fail?
   - Which adversary behaviors or architectural weaknesses are relevant?

4. **Evaluate risk**
   - What is the likelihood and business impact?
   - Which risks require mitigation, transfer, acceptance, or avoidance?

5. **Select security controls**
   - Which preventive, detective, and corrective controls reduce the identified risk?

6. **Translate controls into architecture**
   - Where should the control be enforced?
   - Which identity, network, workload, data, and monitoring boundaries are affected?

7. **Validate and monitor**
   - What evidence demonstrates that the control remains effective?

8. **Govern exceptions and residual risk**
   - What happens when the standard cannot be met?
   - Who owns the remaining risk?
   - When should the decision be reviewed?

---

## TOGAF Alignment

TOGAF provides a structure for connecting business requirements with architecture decisions and managing those decisions throughout an architecture lifecycle.

This project applies that thinking across four architecture perspectives.

| Architecture Perspective | Security Focus |
|---|---|
| **Business Architecture** | Business objectives, stakeholders, regulatory obligations, risk tolerance |
| **Application Architecture** | Application trust relationships, APIs, identity dependencies, service interactions |
| **Data Architecture** | Data classification, protection requirements, telemetry, auditability, data flows |
| **Technology Architecture** | IAM, encryption, network controls, workload protection, monitoring and cloud security services |

The purpose is not to reproduce the complete TOGAF Architecture Development Method. TOGAF concepts are used here to provide structure, traceability, governance, and lifecycle thinking for security architecture.

---

## Risk and Threat Model

Security decisions should consider both business risk and realistic threat scenarios.

This project incorporates several complementary sources of security information:

| Source | Architecture Purpose |
|---|---|
| **NIST CSF** | Organizes security outcomes across Identify, Protect, Detect, Respond, and Recover |
| **ISO/IEC 27001** | Provides governance and information-security control context |
| **CIS Controls** | Provides practical security safeguards |
| **MITRE ATT&CK** | Connects architecture decisions to adversary techniques |
| **CAPEC** | Provides attack-pattern context |
| **CVSS** | Provides one input for vulnerability severity and prioritization |

These frameworks are treated as **decision inputs**, not interchangeable compliance checklists.

A vulnerability or threat should not automatically determine an architecture decision solely because it has a particular framework classification or severity score. Business impact, asset criticality, exposure, existing controls, and compensating controls must also be considered.

---

## Security Control Model

Controls can be evaluated according to how they reduce risk.

### Preventive Controls

Designed to stop an unwanted event before it occurs.

Examples include:

- least-privilege authorization,
- network segmentation,
- encryption requirements,
- workload configuration guardrails,
- secrets-management requirements.

### Detective Controls

Designed to identify security events, policy violations, or control failures.

Examples include:

- audit logging,
- configuration monitoring,
- identity anomaly detection,
- vulnerability scanning,
- security alerting.

### Corrective Controls

Designed to contain, remediate, or recover from a security event or control failure.

Examples include:

- automated remediation,
- credential revocation,
- workload isolation,
- configuration rollback,
- incident-response procedures.

A mature architecture should also define what happens when a control itself fails.

---

## Governance and Architecture Review

Architecture decisions require governance beyond initial design approval.

A security architecture review should be able to answer:

- What business or security requirement is being addressed?
- What threat or failure scenario creates the risk?
- Where is the security boundary?
- Which control mitigates the risk?
- Why was that control selected?
- What telemetry demonstrates that the control is functioning?
- What happens if the control fails?
- Are compensating controls available?
- Who can approve an exception?
- Who owns the residual risk?
- When should the decision be reviewed again?

This turns architecture review from a technology approval exercise into a risk decision.

---

## Exception and Residual-Risk Management

Not every architecture can immediately meet every security requirement.

When an exception is required, the decision should document:

- the unmet requirement,
- the reason the standard cannot currently be met,
- affected systems or data,
- compensating controls,
- business and security impact,
- accountable risk owner,
- security review,
- expiration or review date,
- remediation plan.

Acceptance of an exception does not eliminate risk. It establishes accountability for the remaining risk.

---

## Architecture Lifecycle

Security architecture changes as systems, threats, regulations, and business requirements evolve.

The lifecycle represented by this framework is:

**Business Change → Risk Assessment → Architecture Decision → Control Implementation → Validation → Monitoring → Review**

Triggers for reassessment may include:

- significant architecture changes,
- new regulatory requirements,
- material vulnerabilities,
- changes in data classification,
- new threat intelligence,
- control failures,
- mergers or acquisitions,
- adoption of new cloud platforms or services.

This lifecycle perspective is one of the primary reasons TOGAF concepts are useful for security architecture.

---

## SABSA Relationship

SABSA can complement this approach by providing a more explicitly business-driven security architecture model.

At a high level:

- **TOGAF** helps structure enterprise architecture development and governance.
- **SABSA** provides a security architecture methodology that traces security requirements back to business attributes.

A future iteration of this project could use SABSA business attributes to strengthen traceability between business requirements, security services, control selection, and measurable security outcomes.

This repository currently uses SABSA concepts only as architectural context and does not claim a complete SABSA implementation.

---

## Repository Structure

```text
Architecture/
    Integration_Overview
    Togaf_Explained
    conceptual_togaf_risk_domain_diagram.png
    operational_security_control_flow.png

Governance/
    Compliance_Mapping
    Project_Summary

Infastructure/
    Technologies

Risk_Analysis/
    Threat_Model
    Vulnerability_Analysis

README.md
```

The existing repository uses the directory name `Infastructure`. Renaming it to `Infrastructure` is recommended as part of repository cleanup.

---

## Architecture Artifacts

The repository contains supporting material covering:

- TOGAF and security-risk integration,
- business and governance context,
- security-framework mapping,
- threat modeling,
- vulnerability prioritization,
- cloud security technology responsibilities,
- conceptual architecture relationships,
- operational security-control flow.

These artifacts are intended to demonstrate architecture reasoning rather than represent evidence of a deployed production system.

---

## Key Architecture Takeaway

Cloud security architecture is not primarily the selection of security products or cloud services.

The architecture task is to determine:

**what must be protected, why it matters, what could cause it to fail, which controls reduce that risk, where those controls should be enforced, how their effectiveness will be measured, and who owns the remaining risk.**

TOGAF provides one structure for making those decisions traceable and governable across the architecture lifecycle.
