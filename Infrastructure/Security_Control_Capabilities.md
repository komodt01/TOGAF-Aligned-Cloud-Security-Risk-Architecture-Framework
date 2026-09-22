# Security Control Capabilities

## Purpose

This document identifies security capabilities that may be required to satisfy architecture decisions produced by the risk and governance process in this framework.

The capabilities described here are architectural categories, not evidence that specific technologies have been deployed.

Technology selection should occur after the organization understands:

- the business requirement,
- security outcome,
- relevant threats,
- architecture boundaries,
- operational requirements,
- regulatory obligations,
- risk tolerance.

The same security requirement may be implemented differently across cloud providers and application environments.

---

## Identity and Access Management

### Security Objective

Ensure that identities receive only the access required to perform authorized functions and that trust relationships are explicitly defined.

### Architecture Considerations

- identity lifecycle,
- authentication strength,
- least privilege,
- role and entitlement design,
- privileged access,
- workload identities,
- temporary credentials,
- federation,
- service-to-service authentication,
- access review,
- separation of duties.

### Failure Scenarios

Examples include:

- excessive privilege,
- orphaned accounts,
- compromised credentials,
- overly broad trust relationships,
- unmanaged service identities,
- persistent administrative access.

### Assurance Evidence

Possible evidence includes:

- identity configuration,
- access policies,
- authentication logs,
- entitlement reviews,
- privilege-use telemetry,
- exception records.

---

## Data Protection

### Security Objective

Protect information according to its classification, sensitivity, regulatory requirements, and business value.

### Architecture Considerations

- data classification,
- encryption at rest,
- encryption in transit,
- key management,
- secrets management,
- retention,
- data residency,
- backup protection,
- data-loss prevention,
- access to sensitive information.

### Failure Scenarios

Examples include:

- unauthorized data access,
- unencrypted sensitive information,
- inappropriate key access,
- exposed secrets,
- excessive retention,
- insecure data movement.

### Assurance Evidence

Possible evidence includes:

- encryption configuration,
- key policies,
- access logs,
- classification records,
- secrets-management configuration,
- data-protection alerts.

---

## Network and Connectivity Security

### Security Objective

Limit unauthorized connectivity and control communication across trust boundaries.

### Architecture Considerations

- segmentation,
- ingress controls,
- egress controls,
- private connectivity,
- administrative access paths,
- service-to-service communication,
- network inspection,
- DNS security,
- hybrid connectivity,
- identity-aware access.

### Failure Scenarios

Examples include:

- unintended public exposure,
- unrestricted lateral movement,
- uncontrolled outbound communication,
- bypass of inspection points,
- insecure administrative access.

### Assurance Evidence

Possible evidence includes:

- network policy,
- routing configuration,
- firewall rules,
- flow telemetry,
- exposure assessments,
- connectivity tests.

---

## Workload Security

### Security Objective

Protect compute, container, serverless, and application workloads throughout their lifecycle.

### Architecture Considerations

- secure configuration,
- workload identity,
- image integrity,
- vulnerability management,
- runtime protection,
- patching,
- dependency risk,
- secrets handling,
- attack-surface reduction.

### Failure Scenarios

Examples include:

- vulnerable workloads,
- insecure base images,
- excessive runtime permissions,
- exposed management interfaces,
- outdated dependencies,
- embedded credentials.

### Assurance Evidence

Possible evidence includes:

- configuration assessments,
- vulnerability findings,
- image scan results,
- runtime telemetry,
- patch status,
- security test results.

---

## Logging, Monitoring, and Detection

### Security Objective

Provide sufficient visibility to identify security events, investigate incidents, and verify that important controls are operating.

### Architecture Considerations

- required log sources,
- centralized collection,
- retention,
- integrity,
- detection logic,
- alert routing,
- incident escalation,
- telemetry health,
- monitoring of control failures.

### Failure Scenarios

Examples include:

- required telemetry not generated,
- logging disabled,
- collection pipeline failure,
- insufficient retention,
- ineffective detection,
- alerts not reaching responders.

### Assurance Evidence

Possible evidence includes:

- telemetry health checks,
- log-ingestion status,
- detection results,
- alert records,
- retention configuration,
- incident records.

Logging itself is not assurance. The architecture must also consider whether required telemetry is actually reaching the intended monitoring and response systems.

---

## Vulnerability Management

### Security Objective

Identify and remediate vulnerabilities according to organizational risk.

### Architecture Considerations

- asset criticality,
- vulnerability discovery,
- severity,
- exposure,
- exploitability,
- active exploitation,
- compensating controls,
- remediation ownership,
- remediation timelines.

CVSS may contribute to prioritization but should not be the sole determinant of business risk.

### Failure Scenarios

Examples include:

- incomplete asset coverage,
- vulnerabilities without owners,
- severity-only prioritization,
- remediation delays,
- accepted vulnerabilities without review,
- scanner or telemetry gaps.

### Assurance Evidence

Possible evidence includes:

- vulnerability findings,
- remediation records,
- exception approvals,
- asset coverage reports,
- validation scans,
- risk records.

---

## Secure Software Delivery

### Security Objective

Identify security weaknesses before software and infrastructure changes reach production.

### Architecture Considerations

Depending on the environment, controls may include:

- secrets scanning,
- static application security testing,
- software composition analysis,
- infrastructure-as-code scanning,
- container scanning,
- software bill of materials,
- dynamic testing,
- security gates,
- approval workflows.

### Failure Scenarios

Examples include:

- vulnerable dependencies,
- embedded secrets,
- insecure infrastructure definitions,
- exploitable application code,
- bypassed security gates,
- unreviewed exceptions.

### Assurance Evidence

Possible evidence includes:

- pipeline results,
- scan findings,
- gate decisions,
- exception records,
- approval history,
- remediation evidence.

---

## Configuration and Policy Governance

### Security Objective

Maintain approved security requirements as environments change.

### Architecture Considerations

- configuration baselines,
- preventive guardrails,
- detective policies,
- drift detection,
- automated remediation,
- infrastructure-as-code validation,
- policy-as-code,
- exception governance.

### Failure Scenarios

Examples include:

- configuration drift,
- policy bypass,
- uncontrolled exceptions,
- inconsistent environments,
- failed remediation,
- undocumented deviations.

### Assurance Evidence

Possible evidence includes:

- compliance assessments,
- policy evaluation,
- drift findings,
- remediation results,
- exception records,
- configuration history.

---

## Incident Response and Recovery

### Security Objective

Contain security events, restore required capabilities, and incorporate lessons into architecture.

### Architecture Considerations

- detection-to-response workflow,
- escalation,
- containment,
- credential revocation,
- workload isolation,
- recovery requirements,
- evidence preservation,
- post-incident review.

### Failure Scenarios

Examples include:

- unclear ownership,
- delayed containment,
- missing evidence,
- ineffective recovery,
- repeated architecture weaknesses.

### Assurance Evidence

Possible evidence includes:

- incident records,
- response timelines,
- containment actions,
- recovery tests,
- post-incident findings,
- architecture change records.

---

## Preventive, Detective, and Corrective Coverage

Security capabilities should not be evaluated individually.

For significant risks, architecture should consider whether appropriate layers exist.

| Control Type | Purpose |
|---|---|
| **Preventive** | Reduce the likelihood that the unwanted event occurs |
| **Detective** | Identify that the event or control failure occurred |
| **Corrective** | Contain, remediate, or recover from the event |

A preventive control without detection may fail silently.

A detective control without response may identify risk without reducing it.

A corrective control without governance may repeatedly address symptoms without correcting the architecture.

---

## Technology Selection

Once the required security capabilities are understood, specific technologies can be evaluated according to:

- ability to satisfy the security requirement,
- integration with the existing architecture,
- operational complexity,
- scalability,
- reliability,
- available telemetry,
- automation capability,
- cost,
- organizational expertise,
- vendor dependency,
- regulatory constraints.

Cloud-native and third-party technologies may both be valid depending on these requirements.

---

## Key Principle

The architecture should define **what security capability is required and why** before determining **which product or cloud service provides it**.

Technology implements an architecture decision.

It should not be the reason the architecture decision exists.
