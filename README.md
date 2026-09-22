# TOGAF-Aligned Cloud Security Risk Architecture Framework

## Overview

Cloud security architecture should begin with business risk and security requirements, not with cloud services.

This project demonstrates a structured approach for translating business objectives, regulatory obligations, threat scenarios, and risk tolerance into cloud security architecture decisions. TOGAF concepts provide the architecture lifecycle and governance structure, while security frameworks and threat models provide inputs for determining which controls are appropriate and why.

The objective is to connect:

**Business Requirements → Risk → Threats → Security Controls → Architecture Decisions → Governance and Assurance**

This repository is an architecture and governance project. It does not represent a deployed production environment or claim formal TOGAF, SABSA, NIST, ISO, or CIS certification.

---

## Architecture Problem

Cloud environments can accumulate security controls independently:

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
   - What is the potential business impact?
   - What factors affect likelihood or exposure?
   - Which risks require mitigation, transfer, acceptance, or avoidance?

5. **Select security controls**
   - Which preventive, detective, and corrective controls reduce the identified risk?

6. **Translate controls into architecture**
   - Where should the control be enforced?
   - Which identity, network, workload, data, and monitoring boundaries are affected?

7. **Validate and monitor**
   - What evidence demonstrates that the control is operating as intended?
   - How will control failure be detected?

8. **Govern exceptions and residual risk**
   - What happens when the standard cannot be met?
   - Who owns the remaining risk?
   - When should the decision be reviewed?

This creates traceability from the original business requirement through the resulting architecture decision.

---

## TOGAF Alignment

TOGAF provides a structure for connecting business requirements with architecture decisions and managing those decisions throughout an architecture lifecycle.

This project applies that thinking across four architecture perspectives.

| Architecture Perspective | Security Focus |
|---|---|
| **Business Architecture** | Business objectives, stakeholders, regulatory obligations, risk tolerance |
| **Application Architecture** | Application trust relationships, APIs, identity dependencies, service interactions |
| **Data Architecture** | Data classification, protection requirements, telemetry, auditability, data flows |
| **Technology Architecture** | IAM, encryption, network controls, workload protection, monitoring, and cloud security capabilities |

The purpose is not to reproduce the complete TOGAF Architecture Development Method. Selected TOGAF concepts are used to provide structure, traceability, governance, and lifecycle thinking for security architecture.

---

## Risk and Threat Model

Security decisions should consider both business risk and realistic threat scenarios.

This project uses several complementary sources of security information:

| Source | Architecture Purpose |
|---|---|
| **NIST CSF** | Organizes security outcomes across Govern, Identify, Protect, Detect, Respond, and Recover |
| **ISO/IEC 27001** | Provides information-security governance and risk-management context |
| **CIS Controls** | Provides practical security safeguard context |
| **MITRE ATT&CK** | Provides adversary behavior and technique context |
| **CAPEC** | Provides attack-pattern context |
| **CVSS** | Provides one input for vulnerability technical severity |

These sources are treated as **decision inputs**, not interchangeable compliance checklists.

A framework mapping, threat classification, or vulnerability score does not determine an architecture decision by itself. Business impact, asset criticality, exposure, exploitability, existing controls, trust boundaries, and compensating controls also influence the decision.

---

## Threat-Informed Architecture

Threat modeling connects security requirements to realistic failure scenarios.

The framework considers questions such as:

- Which identities, data, applications, and infrastructure are important?
- Where are the significant trust boundaries?
- How could an attacker cross those boundaries?
- What happens if an authorized identity is compromised?
- What happens if an application or workload is compromised?
- How could privilege be escalated?
- How could security telemetry be disabled or bypassed?
- How could configuration drift create unintended exposure?
- Which controls reduce the likelihood or impact of those scenarios?

Threat modeling is therefore used to influence architecture decisions rather than existing as a separate documentation exercise.

---

## Security Control Model

Controls are evaluated according to how they reduce identified risk.

### Preventive Controls

Designed to stop or limit an unwanted event before it occurs.

Examples include:

- least-privilege authorization,
- network segmentation,
- encryption requirements,
- workload configuration guardrails,
- secrets-management requirements,
- secure administrative access.

### Detective Controls

Designed to identify security events, policy violations, or control failures.

Examples include:

- audit logging,
- configuration monitoring,
- identity anomaly detection,
- vulnerability scanning,
- security alerting,
- telemetry-health monitoring.

### Corrective Controls

Designed to contain, remediate, or recover from a security event or control failure.

Examples include:

- automated remediation,
- credential revocation,
- workload isolation,
- configuration rollback,
- incident-response procedures.

A mature architecture should also define what happens when the security control itself fails.

---

## Control Assurance

Control existence and control effectiveness are different questions.

For important controls, architecture should identify the evidence required to demonstrate that the expected security outcome is being achieved.

Evidence may include:

- authentication events,
- authorization policies,
- access-review records,
- configuration state,
- vulnerability results,
- security telemetry,
- alerts,
- remediation records,
- exception records.

For example, a logging configuration may exist while expected events are no longer reaching the monitoring platform.

The architecture therefore needs to consider both:

**Control Configuration → Control Operation → Evidence → Assurance**

---

## Vulnerability Risk Analysis

Vulnerability severity is an input to risk analysis, not the complete risk decision.

Prioritization should consider:

**Vulnerability → Technical Severity → Exposure → Asset Context → Threat Context → Existing Controls → Business Impact → Remediation Decision**

Relevant factors may include:

- CVSS severity,
- internet exposure,
- exploitability,
- active threat activity,
- asset criticality,
- data sensitivity,
- workload privilege,
- blast radius,
- compensating controls,
- business impact.

This allows remediation decisions to reflect the actual architecture context rather than relying exclusively on a vulnerability score.

---

## Governance and Architecture Review

Architecture decisions require governance beyond initial design approval.

A security architecture review should be able to answer:

- What business or security requirement is being addressed?
- What assets and trust boundaries are affected?
- What threat or failure scenario creates the risk?
- Which control mitigates the risk?
- Why was that control selected?
- What evidence demonstrates that the control is functioning?
- What happens if the control fails?
- Are compensating controls available?
- Who can approve an exception?
- Who owns the residual risk?
- When should the decision be reviewed again?

This turns architecture review from a technology approval exercise into a risk decision.

A useful traceability model is:

**Business Driver → Security Requirement → Risk → Architecture Decision → Control → Evidence → Residual Risk**

---

## Exception and Residual-Risk Management

Not every architecture can immediately meet every security requirement.

When an exception is required, the decision should document:

- the unmet requirement,
- the reason the requirement cannot currently be met,
- affected systems or data,
- associated threat and business impact,
- compensating controls,
- accountable risk owner,
- security review,
- remediation plan,
- expiration or review date.

Acceptance of an exception does not eliminate risk.

It makes the remaining risk visible, accountable, and reviewable.

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

Security architecture is therefore a lifecycle rather than a one-time design activity.

---

## SABSA Relationship

SABSA can complement this approach by providing a more explicitly business-driven security architecture model.

At a high level:

- **TOGAF** helps structure enterprise architecture development and governance.
- **SABSA** provides a security architecture methodology for tracing security requirements to business needs and attributes.

A future iteration of this project could use SABSA concepts to strengthen traceability between business requirements, security services, control selection, and measurable security outcomes.

This repository currently uses SABSA only as architectural context and does not claim a complete SABSA implementation.

---

## Repository Structure

```text
Architecture/
    Integration_Overview.md
    Togaf_Explained.md

Governance/
    Compliance_Mapping.md
    Project_Summary.md

Infrastructure/
    Security_Control_Capabilities.md

Risk_Analysis/
    Threat_Model.md
    Vulnerability_Analysis.md

README.md
technical-case-study.md
```

The repository separates architecture integration, governance, security-control capabilities, and risk analysis so that each concern can be reviewed independently while remaining connected through the overall risk-driven architecture model.

---

## Architecture Artifacts

The repository contains supporting material covering:

- TOGAF and security-risk integration,
- architecture lifecycle and review,
- business and governance context,
- security-framework mapping,
- threat modeling,
- vulnerability risk analysis,
- security-control capabilities,
- exception and residual-risk management,
- a technical case study applying the framework to a cloud architecture scenario.

These artifacts demonstrate architecture reasoning rather than evidence of a deployed production system.

---

## Technical Case Study

The included [Technical Case Study](technical-case-study.md) applies the framework to a business-critical cloud application scenario.

It demonstrates how an architect can evaluate:

- business and security requirements,
- trust boundaries,
- compromised identities,
- application compromise,
- unintended exposure,
- telemetry failure,
- configuration drift,
- identity and data-access decisions,
- preventive, detective, and corrective controls,
- vulnerability prioritization,
- exceptions,
- residual risk,
- Architecture Review Board questions.

The case study is intentionally technology-neutral so that the security reasoning remains applicable across cloud platforms.

---

## Key Architecture Takeaway

Cloud security architecture is not primarily the selection of security products or cloud services.

The architecture task is to determine:

**what must be protected, why it matters, what could cause it to fail, which controls reduce that risk, where those controls should be enforced, how their effectiveness will be demonstrated, what happens when those controls fail, and who owns the remaining risk.**

The resulting decision chain is:

**Business Requirement → Threat and Risk → Architecture Decision → Control → Evidence → Residual Risk → Governance**

That traceability makes security architecture understandable to engineering teams, security leadership, risk owners, and Architecture Review Boards.
