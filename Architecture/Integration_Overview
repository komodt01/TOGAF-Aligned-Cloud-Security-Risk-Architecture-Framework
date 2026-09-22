# Integration Overview

## Purpose

This architecture framework connects business requirements, risk, threats, security controls, technical architecture, and ongoing governance.

The frameworks referenced in this project serve different purposes. They should not be treated as interchangeable checklists or combined simply to increase the number of frameworks represented.

The architecture relationship is:

**Business Requirements → Risk Context → Threat Scenarios → Control Requirements → Architecture Decisions → Implementation → Validation → Governance**

## TOGAF — Architecture Structure and Lifecycle

TOGAF provides the architecture structure used to connect business objectives with architecture decisions and govern those decisions over time.

Within this project, TOGAF concepts help organize security considerations across:

- Business Architecture
- Application Architecture
- Data Architecture
- Technology Architecture

The value is traceability. A technology decision should be explainable in terms of the requirement, risk, or architecture objective that caused it to exist.

TOGAF also reinforces that architecture is not static. Changes in business requirements, technology, threats, regulation, or risk can trigger architecture reassessment.

## Security Frameworks — Security Outcomes and Control Expectations

Security frameworks provide different forms of guidance for determining what security outcomes and safeguards may be required.

### NIST Cybersecurity Framework

NIST CSF provides a structure for organizing cybersecurity outcomes across:

**Govern → Identify → Protect → Detect → Respond → Recover**

This helps ensure the architecture considers more than preventive security controls.

### ISO/IEC 27001

ISO/IEC 27001 provides information-security management and governance context.

Within this architecture, it is useful for connecting technical security decisions with broader areas such as:

- security policy,
- risk management,
- access control,
- asset protection,
- operational security,
- incident management,
- continuous improvement.

### CIS Controls

CIS Controls provide practical safeguards that can help translate higher-level security requirements into more specific technical expectations.

They can inform areas such as:

- identity protection,
- secure configuration,
- vulnerability management,
- logging,
- network monitoring,
- data protection.

These frameworks provide inputs to architecture decisions. They do not determine the architecture by themselves.

## MITRE ATT&CK and CAPEC — Threat Context

Threat modeling helps determine whether proposed controls address realistic attack paths and failure scenarios.

MITRE ATT&CK provides a knowledge base of adversary tactics and techniques that can be used to evaluate how an attacker may attempt to compromise an environment.

CAPEC provides attack-pattern information that can supplement threat analysis.

Within this framework, threat information can be used to ask:

- Which assets or trust boundaries could be targeted?
- Which attack techniques are relevant?
- Which existing controls would prevent or detect the activity?
- Where are control gaps?
- What telemetry would reveal attempted exploitation?
- What happens if the preventive control fails?

Threat frameworks therefore provide context for security architecture decisions rather than functioning as compliance requirements.

## CVSS — Vulnerability Severity Input

CVSS provides a standardized way to describe characteristics and severity of vulnerabilities.

A CVSS score should not be treated as a complete measure of business risk.

Remediation decisions should also consider:

- asset criticality,
- data sensitivity,
- exposure,
- exploitability,
- active exploitation,
- existing controls,
- compensating controls,
- business impact,
- operational constraints.

For example, a high-severity vulnerability affecting an isolated non-production asset may present a different organizational risk than the same vulnerability affecting an internet-facing system processing sensitive data.

CVSS is therefore one input into risk-based vulnerability prioritization.

## Architecture Decision Model

The different sources of information come together during architecture decision-making.

A simplified decision flow is:

1. Identify the business or security requirement.
2. Determine the assets, data, identities, and trust boundaries involved.
3. Identify relevant threats and failure scenarios.
4. Evaluate potential business impact and existing controls.
5. Determine the required security outcome.
6. Select preventive, detective, and corrective controls.
7. Determine where those controls should be enforced.
8. Define telemetry and evidence needed to validate effectiveness.
9. Document tradeoffs and residual risk.
10. Establish exception, ownership, and review requirements.

This creates traceability from the original requirement through the resulting architecture decision.

## Closed-Loop Security Architecture

Security architecture requires continuous feedback.

The operating model is:

**Requirements → Architecture → Controls → Telemetry → Validation → Risk Review → Architecture Adjustment**

Monitoring and security telemetry provide evidence about whether controls continue to operate as intended.

Control failures, new threats, significant vulnerabilities, business changes, and security incidents can then feed back into risk assessment and architecture review.

This closes the gap between architecture design and operational security.

## Key Principle

No single framework determines whether an architecture is secure.

TOGAF provides architecture structure and lifecycle thinking. Security frameworks provide control and governance inputs. Threat models provide adversary context. Vulnerability information provides technical risk inputs. Operational telemetry provides evidence.

The security architect brings those inputs together to make and govern defensible architecture decisions.
