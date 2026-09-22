# Technical Case Study — Risk-Driven Cloud Security Architecture

## Case Study Purpose

This case study demonstrates how the architecture framework can be applied to a cloud security decision.

The scenario is intentionally technology-neutral. The objective is to show the reasoning used to move from a business requirement through threat and risk analysis to architecture controls, assurance, governance, and residual-risk ownership.

---

## Scenario

An organization is expanding a business-critical application into cloud infrastructure.

The application:

- processes sensitive customer information,
- exposes services to external users,
- depends on cloud-native workloads and data services,
- requires administrative access by engineering and operations teams,
- must generate sufficient security evidence for investigation and governance.

The organization needs to move quickly, but security leadership wants assurance that access, data protection, monitoring, and operational controls are designed intentionally rather than added after deployment.

---

## Business Requirements

The architecture must support several business outcomes:

1. Protect sensitive customer information.
2. Maintain availability of the business service.
3. Allow authorized engineering teams to operate the environment.
4. Support security monitoring and incident investigation.
5. Provide evidence that important security controls are operating.
6. Allow the environment to evolve without silently weakening approved security requirements.

These requirements establish the reason security controls are needed.

---

## Architecture Decision Model

The assessment follows this sequence:

**Business Driver → Security Requirement → Threat / Failure Scenario → Risk → Architecture Decision → Control → Evidence → Residual Risk**

This creates traceability between the business requirement and the technical control.

---

## Trust Boundaries

Several important trust boundaries exist within the architecture.

### External User Boundary

External users interact with application interfaces from networks the organization does not control.

The architecture cannot assume that requests crossing this boundary are trustworthy.

### Application-to-Data Boundary

Applications require access to sensitive information.

Application identity and authorization must restrict which workloads can access data and what actions they can perform.

### Administrative Boundary

Engineers and administrators require elevated capabilities.

Administrative access creates a higher-impact trust relationship because compromise or misuse could change infrastructure, identity, logging, or security configuration.

### Cloud Control-Plane Boundary

Cloud administrative APIs can modify the architecture itself.

Control-plane access therefore requires stronger governance, monitoring, and authorization than ordinary application activity.

### Security Telemetry Boundary

Security logs and alerts must remain trustworthy even if an application or workload is compromised.

Telemetry administration should therefore be appropriately separated from ordinary workload administration.

---

## Threat and Failure Scenarios

### Compromised User or Administrative Identity

An attacker obtains valid credentials or session material.

Potential consequences include:

- unauthorized data access,
- privilege escalation,
- infrastructure modification,
- persistence,
- disabling security controls.

Architecture implications include strong authentication, least privilege, controlled privilege escalation, short-lived credentials where practical, and monitoring of privileged activity.

---

### Application Compromise

An attacker exploits an application weakness or vulnerable dependency.

Potential consequences include:

- access to application data,
- workload compromise,
- credential theft,
- lateral movement,
- downstream service compromise.

Architecture should limit the privileges and connectivity available to the compromised workload so that application compromise does not automatically become broader environment compromise.

---

### Unintended External Exposure

A configuration change exposes a workload, data service, or administrative interface.

Preventive controls should restrict exposure by default.

Detective controls should identify configuration drift or unexpected reachability.

Corrective processes should define how unauthorized exposure is removed and investigated.

---

### Security Telemetry Failure

Logging remains configured but events stop reaching the expected monitoring destination.

This creates an important distinction:

**configuration compliance does not necessarily demonstrate telemetry health.**

The architecture therefore requires assurance that expected security events are actually being generated, transported, received, and available for investigation.

---

### Privilege or Configuration Drift

An approved architecture changes over time through deployment automation, manual administration, emergency changes, or configuration error.

The security architecture must therefore account for lifecycle governance rather than treating initial deployment as the end of the architecture process.

---

## Architecture Decisions

### Decision 1 — Identity Is the Primary Access Boundary

Access should be granted through managed identities, roles, and explicitly defined authorization rather than broadly shared credentials.

**Security objective:** reduce unauthorized access and credential-related blast radius.

**Control types:**

- Preventive: strong authentication, least privilege, scoped roles, short-lived credentials where appropriate.
- Detective: authentication and privilege-use monitoring.
- Corrective: session revocation, credential rotation, privilege removal.

**Tradeoff:** stronger identity controls can increase administrative complexity and require additional lifecycle processes.

---

### Decision 2 — Sensitive Data Access Is Explicitly Authorized

Applications and administrators should receive only the data access required for their responsibilities.

Authorization should be enforced at appropriate service and data boundaries rather than relying exclusively on application behavior.

**Security objective:** limit unauthorized disclosure or modification of sensitive information.

**Control types:**

- Preventive: scoped authorization, encryption, controlled service access.
- Detective: data-access telemetry and anomalous-use monitoring.
- Corrective: access revocation, credential rotation, investigation and containment.

**Tradeoff:** granular authorization requires stronger ownership and policy management.

---

### Decision 3 — External Exposure Is Explicit, Not Accidental

Public accessibility should be an architecture decision.

Systems that do not require direct external access should use restricted connectivity appropriate to their design.

**Security objective:** reduce unnecessary attack surface.

**Control types:**

- Preventive: secure network defaults, restricted ingress, private connectivity where appropriate.
- Detective: configuration monitoring and exposure assessment.
- Corrective: isolation, configuration rollback, or removal of unintended access.

**Tradeoff:** private connectivity and segmentation can increase network complexity and operational dependencies.

---

### Decision 4 — Security Telemetry Is a Required Architecture Capability

Security-relevant activity must generate telemetry sufficient for detection, investigation, and governance.

The architecture must consider both telemetry configuration and telemetry health.

**Security objective:** maintain security visibility.

**Control types:**

- Preventive: protected logging configuration and restricted administration.
- Detective: monitoring of security events and monitoring of telemetry health itself.
- Corrective: restore failed telemetry, investigate visibility gaps, and validate affected systems.

**Tradeoff:** additional telemetry increases ingestion, storage, operational, and tuning costs.

---

### Decision 5 — Security Controls Require Evidence

A control should not be considered effective solely because it exists in an architecture document or configuration.

Important controls require evidence.

Examples include:

- authentication events,
- authorization configuration,
- policy evaluations,
- configuration state,
- security alerts,
- vulnerability results,
- access reviews,
- remediation records.

**Security objective:** provide assurance that architecture requirements remain effective.

**Tradeoff:** evidence collection creates governance and operational overhead that must be planned rather than treated as an audit-only activity.

---

## Control Failure

Architecture review should also consider what happens when the security control itself fails.

Examples include:

- authentication service unavailable,
- logging pipeline stops ingesting,
- vulnerability scanning misses an asset,
- configuration policy is disabled,
- automated remediation fails,
- credential rotation fails,
- security alert is generated but never reaches a responder.

For important controls, the architecture should identify:

1. how failure is detected,
2. who owns the failure,
3. what response is expected,
4. whether a compensating control exists,
5. when architecture or risk review is required.

---

## Vulnerability Prioritization

Vulnerabilities are prioritized using risk context rather than CVSS alone.

Relevant factors include:

- technical severity,
- exposure,
- exploitability,
- active threat activity,
- asset criticality,
- data sensitivity,
- workload privilege,
- blast radius,
- existing controls,
- business impact.

A critical vulnerability on an isolated low-value workload may present a different organizational risk than a high-severity vulnerability on an internet-facing service processing sensitive information.

The remediation decision should reflect that difference.

---

## Exception Scenario

Assume an important component cannot be remediated within the expected timeframe because the required update creates a compatibility issue with a critical business application.

Simply leaving the vulnerability unresolved would create an unmanaged architecture gap.

The exception should document:

- affected component,
- security requirement that cannot currently be met,
- associated threat,
- business impact,
- compensating controls,
- residual risk,
- accountable risk owner,
- remediation plan,
- expiration or review date.

Possible compensating controls could include stronger isolation, reduced access, additional monitoring, or temporary restriction of vulnerable functionality.

The exception does not eliminate the risk.

It makes the risk visible, owned, and reviewable.

---

## Architecture Review Board Questions

Before approval, an Architecture Review Board should be able to answer:

- What business requirement is being protected?
- Which assets and trust boundaries are affected?
- What credible threats or failure scenarios were considered?
- Which controls reduce those risks?
- Why were those controls selected?
- What evidence demonstrates that the controls are functioning?
- What happens if a control fails?
- Are compensating controls required?
- Are any exceptions being requested?
- Who owns the residual risk?
- When will exceptions and architecture decisions be reviewed?

If those questions cannot be answered, the architecture may not yet be ready for approval.

---

## Residual Risk

Even after the proposed controls are applied, risk remains.

Examples include:

- valid credentials may still be abused,
- application vulnerabilities may remain undiscovered,
- authorized administrators may misuse privilege,
- monitoring may not detect every malicious action,
- configuration changes may temporarily create exposure,
- third-party or cloud-provider dependencies may fail.

The objective of security architecture is not to claim that risk has been eliminated.

The objective is to ensure that significant risk is:

**identified → reduced → observable → governed → owned.**

---

## Architecture Lifecycle

Approval is not the end of the architecture process.

The lifecycle continues through:

**Architecture Decision → Implementation → Evidence → Monitoring → Risk Review → Architecture Adjustment**

New vulnerabilities, threat intelligence, incidents, business requirements, technology changes, and control failures may all justify revisiting an earlier architecture decision.

This feedback loop keeps security architecture connected to the operating environment.

---

## Technical Outcome

The resulting architecture does not depend on a particular cloud provider or security product.

Instead, it establishes required security outcomes for:

- identity,
- authorization,
- data protection,
- network exposure,
- workload security,
- telemetry,
- vulnerability management,
- incident response,
- exception governance,
- assurance.

Specific technologies can then be selected according to platform requirements while preserving the intended security outcome.

---

## Key Architecture Takeaway

Security architecture is not the act of selecting the largest possible set of security controls.

It is the process of connecting:

**Business Requirement → Threat and Risk → Architecture Decision → Control → Evidence → Residual Risk → Governance**

That traceability allows technical teams, security leadership, risk owners, and an Architecture Review Board to understand not only **what** security controls exist, but **why they exist and how the organization knows they are working**.
