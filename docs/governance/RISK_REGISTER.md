# Risk Register

> **Status:** PROPOSED - Subject to owner approval

## Risk Rating Scale

| Rating | Probability | Impact | Description |
|---|---|---|---|
| CRITICAL | > 60% | Severe | Likely and catastrophic |
| HIGH | 30-60% | Major | Possible and very impactful |
| MEDIUM | 10-30% | Moderate | Unlikely but harmful |
| LOW | < 10% | Minor | Very unlikely and minor impact |

## Risks

| ID | Risk | Category | Probability | Impact | Rating | Mitigation | Owner | Status |
|---|---|---|---|---|---|---|---|---|
| R-001 | Agent produces incorrect requirements | Requirements | MEDIUM | HIGH | HIGH | Adversarial review, evidence verification, ambiguity detection | Requirements Discovery Team | OPEN |
| R-002 | Security vulnerability introduced in generated code | Security | MEDIUM | HIGH | HIGH | SDL gates, security review team, threat modeling | Security Threat Intelligence Team | OPEN |
| R-003 | Agent escalates beyond intended scope | Governance | LOW | CRITICAL | HIGH | Authority model, capability lifecycle, no-silent-expansion rule | Factory Lead Agent | OPEN |
| R-004 | Outdated or vulnerable dependencies used | Supply Chain | HIGH | MEDIUM | MEDIUM | Dependency scanning, pinning, regular updates | Delivery Engineering Team | OPEN |
| R-005 | Hallucinated or fabricated evidence | Validation | MEDIUM | HIGH | HIGH | Independent verification, evidence provenance tracking | Independent Verification Team | OPEN |
| R-006 | Model provider API changes break factory | External | LOW | MEDIUM | MEDIUM | Capability monitoring, adapter abstraction | Capability Research Lab | OPEN |
| R-007 | No license selected blocks adoption | Governance | HIGH | LOW | MEDIUM | License decision tracked as PENDING | Human Project Owner | OPEN |
| R-008 | Agent credentials or secrets leaked | Security | LOW | CRITICAL | HIGH | No secrets in generated files, secrets scanning, least privilege | Security Threat Intelligence Team | OPEN |
| R-009 | Incomplete traceability links | Traceability | MEDIUM | MEDIUM | MEDIUM | Traceability model, orphan detection, regular audits | Architecture Traceability Team | OPEN |
| R-010 | Agent skill supply-chain compromise | Supply Chain | LOW | HIGH | MEDIUM | Skill audit before adoption, integrity verification | Capability Research Lab | OPEN |

## Risk Review Cadence

- Risks reviewed quarterly or after any HIGH/CRITICAL incident.
- New risks added during phase gate reviews.
- Mitigations tracked as actionable items in the factory backlog.
