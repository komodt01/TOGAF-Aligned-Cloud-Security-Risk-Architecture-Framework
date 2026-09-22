# Security Framework Mapping

## Purpose

Security frameworks and standards provide useful inputs to architecture, but compliance mapping should not be confused with proof that a control is implemented or operating effectively.

This document demonstrates how security requirements can be traced across several commonly used frameworks and then translated into architecture considerations.

The relationship is:

**Framework Requirement → Security Outcome → Architecture Requirement → Control → Evidence**

Actual compliance would require validation of the applicable framework version, organizational scope, control implementation, operating effectiveness, and supporting evidence.

---

## Mapping Principles

This project uses several principles when translating framework requirements into architecture.

### Requirements Before Technology

A framework identifies an expected security outcome or control objective.

Architecture determines how that requirement should be satisfied within the system context.

Technology is selected afterward.

### Comparable Outcomes, Different Implementations

A requirement such as least privilege may be implemented differently across cloud providers and applications.

The architecture standard should therefore focus on the required security outcome rather than requiring identical technology everywhere.

### Evidence Is Part of the Architecture

A control is incomplete if the organization cannot determine whether it is operating as intended.

Architecture should identify the evidence required to validate important security controls.

### Mapping Does Not Equal Compliance

A relationship between an architecture control and a security framework does not demonstrate certification or compliance.

Formal compliance requires additional scoping, implementation, testing, evidence, governance, and independent assessment where applicable.

---

## NIST Cybersecurity Framework

The NIST Cybersecurity Framework can be used to organize security outcomes across:

**Govern → Identify → Protect → Detect → Respond → Recover**

| CSF Function | Architecture Question | Example Security Outcome |
|---|---|---|
| **Govern** | Who owns security requirements, risk, policy, and exceptions? | Security decisions have accountable ownership and governance |
| **Identify** | What assets, identities, data, dependencies, and risks exist? | Critical resources and risks are understood |
| **Protect** | Which controls reduce the likelihood or impact of compromise? | Access, data, workloads, and infrastructure are appropriately protected |
| **Detect** | How will control failures and suspicious activity be identified? | Required security events produce actionable telemetry |
| **Respond** | What happens when a security event occurs? | Response responsibilities and containment actions are defined |
| **Recover** | How will capabilities be restored and lessons incorporated? | Recovery requirements exist and findings feed architecture improvement |

This framework helps prevent architecture from focusing exclusively on preventive controls.

---

## ISO/IEC 27001

ISO/IEC 27001 provides an information security management framework that connects organizational governance, risk management, policies, controls, and continual improvement.

For architecture purposes, relevant considerations may include:

| Security Area | Architecture Consideration |
|---|---|
| Organizational governance | Security ownership, policy, responsibilities, risk decisions |
| Asset management | Resource ownership, classification, inventory, lifecycle |
| Identity and access | Authentication, authorization, privilege management, access review |
| Data protection | Classification, encryption, retention, handling requirements |
| Operations security | Configuration, vulnerability management, monitoring, change control |
| Secure development | Security requirements, architecture review, testing, dependency risk |
| Incident management | Detection, escalation, response, lessons learned |
| Supplier relationships | External dependencies, third-party access, inherited controls |
| Compliance | Regulatory obligations, evidence, control traceability |

Specific ISO/IEC 27001 and ISO/IEC 27002 control identifiers should be validated against the version and scope being used by an organization before being included in formal compliance documentation.

---

## CIS Controls

CIS Controls provide practical safeguards that can help translate security requirements into technical expectations.

| Security Area | Architecture Consideration |
|---|---|
| Asset inventory | Systems and cloud resources should have identifiable ownership and lifecycle |
| Software inventory | Authorized software and dependencies should be understood |
| Data protection | Sensitive information should receive protection appropriate to classification |
| Secure configuration | Approved configuration baselines and drift management should exist |
| Account management | Accounts should be governed throughout their lifecycle |
| Access control | Access should follow least privilege and appropriate authentication requirements |
| Vulnerability management | Vulnerabilities should be identified and prioritized according to organizational risk |
| Audit logging | Security-relevant activity should generate appropriate telemetry |
| Network monitoring | Network activity should be observable where required by risk |
| Incident response | Response responsibilities and processes should be established |

CIS safeguards can inform technical implementation while architecture determines where and how those safeguards apply.

---

## Cross-Framework Example

Consider a requirement to protect privileged administrative access.

Different frameworks may express related expectations differently, but architecture can translate them into a common security outcome.

**Business Concern**

Compromise of privileged access could result in unauthorized changes, data exposure, or service disruption.

**Security Outcome**

Privileged access must be strongly authenticated, limited to authorized administrators, appropriately scoped, monitored, and reviewable.

**Architecture Requirements**

The architecture may require:

- strong authentication,
- least privilege,
- separation of administrative roles,
- temporary or time-bound privilege where appropriate,
- controlled administrative paths,
- audit logging,
- access review,
- detection of suspicious privileged activity.

**Possible Evidence**

Evidence could include:

- identity configuration,
- authorization policy,
- access-review records,
- authentication logs,
- privilege-use telemetry,
- alerts,
- exception records.

The technology used to implement these requirements may differ among platforms, but the expected security outcome remains consistent.

---

## Control Traceability

A useful architecture traceability model is:

| Layer | Question |
|---|---|
| **Business Requirement** | Why does this matter? |
| **Risk** | What could happen if the requirement is not met? |
| **Security Requirement** | What outcome must be achieved? |
| **Architecture Decision** | How will the architecture address the requirement? |
| **Control** | What prevents, detects, or corrects the failure? |
| **Evidence** | How do we know the control is operating? |
| **Residual Risk** | What risk remains? |
| **Ownership** | Who is accountable for that remaining risk? |

This provides more useful architecture governance than simply listing framework control identifiers.

---

## Exceptions

If an architecture cannot meet a required security outcome, the gap should not disappear simply because another control exists.

The exception process should identify:

- the unmet requirement,
- affected architecture,
- associated risk,
- compensating controls,
- accountable owner,
- remediation plan,
- expiration or review date.

Framework mapping can then show both the intended control and the approved exception.

---

## Key Takeaway

Security frameworks help define expected outcomes and safeguards.

Architecture determines how those expectations apply to a particular system, where controls should be enforced, how their effectiveness will be demonstrated, and who owns the remaining risk.

**Mapping establishes traceability. Evidence and assurance establish whether the control actually works.**
