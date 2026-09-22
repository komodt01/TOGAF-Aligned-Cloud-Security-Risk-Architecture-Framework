# Threat Model

## Purpose

Threat modeling provides adversary and failure context for security architecture decisions.

The objective is not to map every possible threat to a framework identifier. The objective is to identify credible scenarios that could cause important business or security requirements to fail and determine whether the architecture provides appropriate preventive, detective, and corrective controls.

Threat information can be informed by sources such as MITRE ATT&CK and CAPEC, but architecture decisions must also consider the specific system, assets, trust boundaries, exposure, and business impact.

---

## Threat Modeling Approach

The model follows this sequence:

**Asset / Business Capability → Trust Boundary → Threat Scenario → Impact → Controls → Detection → Response → Residual Risk**

For each significant scenario, the architect should ask:

1. What asset or capability is being protected?
2. Where does trust change?
3. What could an attacker or failure condition exploit?
4. What would the business impact be?
5. What prevents the scenario?
6. How would the organization know the preventive control failed?
7. What happens after detection?
8. What risk remains?

This prevents threat modeling from becoming only a list of attack techniques.

---

## Primary Assets and Security Interests

A cloud architecture may contain several categories of assets requiring protection.

### Identities and Credentials

Includes:

- workforce identities,
- privileged identities,
- workload identities,
- API credentials,
- tokens,
- secrets,
- federation relationships.

Primary security interests include preventing unauthorized access, privilege escalation, impersonation, and persistence.

### Sensitive Data

Includes:

- customer information,
- regulated information,
- credentials,
- intellectual property,
- security telemetry,
- business-sensitive records.

Primary security interests include confidentiality, integrity, availability, appropriate use, and traceability.

### Applications and APIs

Includes:

- externally accessible applications,
- internal services,
- APIs,
- administrative interfaces,
- service-to-service communication.

Primary security interests include authentication, authorization, input handling, availability, and protection of trust relationships.

### Cloud Control Plane

Includes administrative capabilities used to modify:

- identity,
- networking,
- logging,
- workloads,
- data access,
- security configuration.

Compromise of the control plane can allow an attacker to change the security architecture itself.

### Security Telemetry

Includes:

- audit logs,
- authentication events,
- network telemetry,
- security alerts,
- vulnerability findings,
- configuration state.

Telemetry must be protected because attackers may attempt to disable, modify, or bypass visibility.

---

## Representative Threat Scenarios

### Scenario 1 — Compromised Identity or Credential

**Threat**

An attacker obtains valid credentials, tokens, secrets, or session material and uses them to access cloud resources.

**Potential Impact**

- unauthorized data access,
- privilege escalation,
- infrastructure modification,
- persistence,
- lateral movement,
- service disruption.

**Preventive Controls**

Potential architecture requirements include:

- strong authentication,
- least privilege,
- short-lived credentials,
- workload identity,
- controlled federation,
- secrets management,
- restricted trust relationships.

**Detective Controls**

Potential detection includes:

- unusual authentication behavior,
- unexpected privilege use,
- anomalous API activity,
- access from unexpected locations or systems,
- unusual resource access.

**Corrective Controls**

Possible response includes:

- session revocation,
- credential rotation,
- privilege removal,
- account containment,
- investigation of affected resources.

**Residual Risk**

Valid credentials may allow malicious activity to initially resemble legitimate activity. Identity controls therefore require behavioral and activity monitoring in addition to authentication.

---

### Scenario 2 — Privilege Escalation or Persistence

**Threat**

An attacker or unauthorized user modifies roles, policies, trust relationships, accounts, or other authorization mechanisms to gain additional access or maintain persistence.

**Potential Impact**

- administrative compromise,
- expanded blast radius,
- long-term unauthorized access,
- bypass of security controls.

**Preventive Controls**

Potential requirements include:

- separation of duties,
- restricted privilege-management permissions,
- approval for sensitive access changes,
- policy guardrails,
- limited administrative paths.

**Detective Controls**

Monitor for:

- creation of privileged identities,
- changes to trust policies,
- privilege assignments,
- unusual role assumptions,
- changes to authorization boundaries.

**Corrective Controls**

Possible response includes:

- removing unauthorized access,
- revoking sessions,
- restoring approved policy,
- investigating related activity.

**Residual Risk**

Authorized administrators may legitimately perform many of these actions, requiring contextual monitoring and governance rather than relying only on static rules.

---

### Scenario 3 — Security Telemetry Disabled or Bypassed

**Threat**

Logging, monitoring, or security tooling is disabled, modified, or bypassed.

**Potential Impact**

The organization may lose the ability to:

- detect attacks,
- investigate incidents,
- demonstrate control effectiveness,
- reconstruct events,
- meet audit or regulatory requirements.

**Preventive Controls**

Potential requirements include:

- restricted logging administration,
- protected log destinations,
- configuration guardrails,
- separation between workload and security administration.

**Detective Controls**

Detection should include monitoring the monitoring system itself.

Examples include:

- missing expected telemetry,
- configuration changes,
- ingestion failures,
- unexpected reductions in event volume,
- disabled security services.

**Corrective Controls**

Possible response includes:

- restoring telemetry,
- escalating monitoring failures,
- investigating the period of lost visibility,
- validating affected systems.

**Residual Risk**

A logging system can appear configured correctly while telemetry is no longer reaching the destination. Configuration compliance alone therefore does not demonstrate telemetry health.

---

### Scenario 4 — Unintended External Exposure

**Threat**

A workload, data store, API, or administrative interface becomes reachable from an unintended network or trust zone.

**Potential Impact**

- unauthorized access,
- exploitation of vulnerable services,
- data exposure,
- increased attack surface.

**Preventive Controls**

Potential requirements include:

- secure network defaults,
- restricted ingress,
- private connectivity,
- explicit exposure approval,
- configuration guardrails.

**Detective Controls**

Potential detection includes:

- exposure assessments,
- configuration monitoring,
- network telemetry,
- external attack-surface monitoring,
- policy violations.

**Corrective Controls**

Possible response includes:

- removing public access,
- isolating the resource,
- restoring approved configuration,
- investigating whether exposure was exploited.

**Residual Risk**

Some systems must remain externally accessible. For those systems, exposure cannot be eliminated and must instead be managed through layered controls.

---

### Scenario 5 — Application or API Exploitation

**Threat**

An attacker exploits an application weakness, vulnerable dependency, insecure API, or improper input handling.

**Potential Impact**

- unauthorized data access,
- application compromise,
- remote code execution,
- service disruption,
- downstream compromise.

**Preventive Controls**

Potential requirements include:

- secure development practices,
- dependency management,
- input validation,
- authentication and authorization,
- security testing,
- workload hardening.

**Detective Controls**

Potential detection includes:

- application security telemetry,
- abnormal API behavior,
- runtime alerts,
- vulnerability findings,
- suspicious workload activity.

**Corrective Controls**

Possible response includes:

- blocking malicious requests,
- isolating affected workloads,
- patching vulnerabilities,
- rotating exposed credentials,
- deploying corrected software.

**Residual Risk**

Application security controls cannot guarantee that all exploitable weaknesses are discovered before deployment. Runtime detection and incident response remain necessary.

---

### Scenario 6 — Security Misconfiguration or Control Drift

**Threat**

A previously approved security configuration changes through manual modification, automation, deployment, or configuration error.

**Potential Impact**

- excessive access,
- public exposure,
- disabled security controls,
- loss of telemetry,
- noncompliance with architecture requirements.

**Preventive Controls**

Potential requirements include:

- infrastructure-as-code,
- policy guardrails,
- change control,
- secure configuration baselines,
- restricted administrative access.

**Detective Controls**

Potential detection includes:

- configuration monitoring,
- drift detection,
- policy evaluation,
- security posture assessment.

**Corrective Controls**

Possible response includes:

- automated remediation for well-understood conditions,
- rollback,
- manual remediation,
- escalation for architecture review.

**Residual Risk**

Automated remediation itself can create operational impact if the architecture does not account for legitimate exceptions.

---

## Threat-Informed Control Selection

Threat frameworks should inform control decisions, not dictate them.

A MITRE ATT&CK technique may identify an adversary behavior worth considering, but architecture must still determine:

- whether the technique is relevant to the environment,
- which assets could be affected,
- which trust boundaries are involved,
- what business impact could result,
- which existing controls already reduce the risk,
- whether additional controls are justified.

The same ATT&CK technique may therefore result in different architecture decisions in different systems.

---

## Control Failure

Threat modeling should include failure of the security controls themselves.

Examples include:

- MFA unavailable or bypassed,
- telemetry pipeline failure,
- vulnerability scanner coverage gaps,
- security policy disabled,
- automated remediation failure,
- secrets rotation failure,
- alert not reaching responders.

Architecture should define how important control failures are detected and who is responsible for responding.

---

## Exception Governance

A threat may be understood even when the organization cannot immediately implement the preferred control.

In those situations, the architecture should document:

- the threat,
- affected asset,
- business impact,
- missing control,
- compensating controls,
- residual risk,
- accountable owner,
- remediation plan,
- review or expiration date.

This keeps risk visible rather than allowing an architectural limitation to become an undocumented exception.

---

## Key Takeaway

Threat modeling is most useful when it changes an architecture decision.

The objective is not simply to demonstrate knowledge of attack techniques.

The architect must connect:

**Threat → Business Impact → Security Requirement → Control → Detection → Response → Residual Risk**

That connection makes threat modeling actionable within architecture governance.
