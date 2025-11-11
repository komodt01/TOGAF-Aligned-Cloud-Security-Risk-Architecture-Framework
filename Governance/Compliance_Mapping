# Compliance Mapping – NIST CSF, ISO 27001, CIS Controls

This mapping shows how key controls are implemented and evidenced in cloud platforms.

## NIST Cybersecurity Framework (CSF)
| Function | Example Category/ID | Implementation / Evidence |
|---------|----------------------|---------------------------|
| Identify | ID.AM-1 Asset Management | Terraform/IaC inventory + tags; CMDB alignment |
| Protect  | PR.AC-5 Network & Identity Access | IAM roles/policies; least-privilege; conditional access |
| Protect  | PR.DS-1 Data at Rest | KMS/customer-managed keys; encryption policies |
| Detect   | DE.CM-7 Monitoring | CloudWatch/Log Analytics metrics, SIEM rules |
| Respond  | RS.MI-1 Mitigation | Runbooks; automation (Lambda/Logic App) for certain misconfigs |
| Recover  | RC.IM-1 Improvements | Post-incident lessons → backlog; Phase H updates |

## ISO/IEC 27001 (Selected Annex A)
| Annex A Control | Cloud Interpretation |
|-----------------|---------------------|
| A.8 Asset Management | Resource inventory, ownership, tagging standards |
| A.9 Access Control | RBAC/ABAC, MFA, temporary credentials, session policies |
| A.12 Operations Security | Change management, anti-malware, logging, vulnerability mgmt |
| A.14 System Acquisition/Dev | Secure SDLC, IaC reviews, dependency scanning, SBOM |
| A.18 Compliance | Evidence retention, audit facilitation, legal/regulatory mapping |

## CIS Critical Security Controls (Selected)
| Control | Intent | Examples |
|--------|--------|----------|
| CSC 1–2 Inventory | Know assets and software | IaC source of truth; drift detection |
| CSC 3 Vulnerability Mgmt | Continuous scanning & patching | Inspector/Trivy/OpenVAS + CVSS SLAs |
| CSC 5 Account Mgmt | Strong identity control | Just-in-time access; key rotation; strong trust policies |
| CSC 6 Access Control Mgmt | Least privilege | Role boundaries; permission baselines |
| CSC 8 Audit Logs | Central collection & retention | SIEM ingest, immutability controls |

> This table is not exhaustive; it demonstrates traceability points a reviewer would expect.
