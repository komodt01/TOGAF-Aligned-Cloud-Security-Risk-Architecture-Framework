# TOGAF-Aligned-Cloud-Security-Risk-Architecture-Framework
> **Security architecture is most effective when it directly supports business outcomes.**
> This framework aligns cloud security capabilities with organizational risk tolerance,
> regulatory requirements, and operational realities — structured using TOGAF’s
> lifecycle and architecture domains to ensure consistency, justification, and governance
> of security decisions across AWS, Azure, and GCP.

# TOGAF-Aligned Cloud Security Risk & Architecture Framework

This project demonstrates how cloud security capabilities can be structured using the **TOGAF Architecture Development Method (ADM)** to align **business drivers, risk tolerance, threat intelligence, and platform security controls**.

The intent is not to replicate TOGAF certification artifacts, but to apply TOGAF’s **architecture lifecycle and domain structure** to provide clarity, traceability, and governance to cloud security decisions.

---

## Architecture Intent

Security controls are most effective when they are:

- **Traceable** to business requirements,
- **Justifiable** in terms of mitigating material risk,
- **Measurable** in how they affect operational outcomes, and
- **Adaptable** as threats and business needs change.

This framework connects:

- **Business risk and regulatory obligations**
- **Security control baselines** (NIST CSF, ISO 27001, CIS Controls)
- **Adversary behaviors** (MITRE ATT&CK, CAPEC)
- **Vulnerability severity and prioritization** (CVSS v3.1)
- **Continuous governance and architecture evolution** (TOGAF Phase H)

The outcome is a **threat-informed, risk-aligned, governance-backed cloud security architecture**.

---

## TOGAF Architecture Domains (Applied in This Project)

| Domain | Focus | Representation in This Repository |
|-------|-------|-----------------------------------|
| **Business Architecture** | Business drivers, risk appetite, compliance posture | `governance/project_summary.md` |
| **Application Architecture** | Services, identity boundaries, API trust relationships | `governance/project_summary.md` |
| **Data Architecture** | Event visibility, log flows, data movement & classification | `architecture/integration_overview.md` |
| **Technology Architecture** | IAM, encryption, scanning, monitoring, network segmentation | `infrastructure/technologies.md` |

TOGAF provides the **structure and lifecycle** for how architecture evolves and is governed.

---

## Risk-Based Security Model

This framework integrates multiple security standards and threat models:

| Framework | Role in the Architecture |
|----------|--------------------------|
| **NIST CSF** | Defines security function alignment (Identify → Protect → Detect → Respond → Recover) |
| **ISO 27001** | Provides governance & control objective anchors |
| **CIS Controls** | Defines enforceable security safeguards and technical expectations |
| **MITRE ATT&CK / CAPEC** | Ensures controls address real-world adversary behaviors |
| **CVSS v3.1** | Quantifies vulnerability severity for prioritized remediation |

The result is **risk-based prioritization**, not equal-effort security.

---

## Design Motivation and Rationale

The purpose of this project is to **demonstrate architectural reasoning** rather than simply tool configuration.

Using TOGAF provides:

- A **repeatable structure** to document cloud security architecture,
- A **lifecycle perspective** rather than point-in-time design,
- A way to **trace architecture decisions to business and risk drivers**, and
- A framework for **continuous adjustment** based on threat and operational feedback.

This project reflects the role of the **security architect** as a bridge between:
**business → risk → architectural decisions → platform enforcement.**

---

## Future Direction: Extending With SABSA (Correctly Explained)

**SABSA (Sherwood Applied Business Security Architecture)** is a **business-driven security architecture framework** that begins with identifying **Business Attributes** such as confidentiality requirements, trust models, reliability needs, regulatory conditions, and risk tolerance.

SABSA structures security architecture across **six layers**, each answering a different “architecture question”:

| SABSA Layer | Focus | Outcome |
|-------------|-------|---------|
| **Contextual** | Business purpose, stakeholders, mission | Why security is needed |
| **Conceptual** | Security concepts and trust expectations | What security needs to achieve |
| **Logical** | Security services and relational structures | How security functions should interact |
| **Physical** | Technology platform designs | Which architectural patterns support the model |
| **Component** | Product/tool selection and configuration | Which tools and settings realize the model |
| **Operational** | Monitoring and ongoing assurance | How security outcomes are validated over time |

### Why SABSA Is the Next Iteration
- TOGAF organizes **how architecture evolves**
- **SABSA defines why specific security controls must exist**
- Combining the two yields **traceable, governed, business-aligned security architecture**

This project intentionally establishes the **TOGAF structural foundation** so that a **SABSA attribute-driven security model** can be layered on next.

---

## Repository Deliverables

| File | Description |
|------|-------------|
| `architecture/integration_overview.md` | How TOGAF, NIST, MITRE, and CVSS interconnect |
| `architecture/conceptual_togaf_risk_domain_diagram.png` | Strategic architecture layer model |
| `architecture/operational_security_control_flow.png` | Control enforcement, telemetry, & governance flow |
| `governance/project_summary.md` | TOGAF ADM phase alignment and business context |
| `governance/compliance_mapping.md` | NIST / ISO / CIS control traceability |
| `risk_analysis/threat_model.md` | MITRE ATT&CK + CAPEC adversary mapping |
| `risk_analysis/vulnerability_analysis.md` | CVSS-based prioritization and remediation outcomes |
| `infrastructure/technologies.md` | Cloud platform control responsibilities & implementation notes |

---

## Certification Note (Important)

> This project uses TOGAF and SABSA **concepts for architectural reasoning only**.  
> No certification, endorsement, or formal affiliation is claimed or implied.

