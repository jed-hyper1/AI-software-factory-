# Secure Development Lifecycle

> **Status:** PROPOSED

## Purpose

Integrate security into every phase of the AI Software Factory development
lifecycle, from requirements through release.

## Lifecycle Phases and Security Activities

| Phase | Security Activities | Responsible Team |
|---|---|---|
| Requirements Discovery | Security requirements elicitation, regulatory mapping | Requirements Discovery + Security Teams |
| Architecture Review | Threat modeling, security design review | Architecture Traceability + Security Teams |
| Implementation | Secure coding, secrets protection, least privilege | Delivery Engineering + Security Teams |
| Testing | Security testing, vulnerability scanning | Independent Verification + Security Teams |
| Adversarial Review | Security-focused challenge of all deliverables | Adversarial Review Team |
| Release | Final security sign-off, residual risk acceptance | Security Team + Owner |

## Security Requirements

### REQ-SEC Series

| ID | Requirement | Status |
|---|---|---|
| REQ-SEC-001 | All evidence records must be immutable | PROPOSED |
| REQ-SEC-002 | No secrets, credentials, tokens, or personal data in repository | PROPOSED |
| REQ-SEC-003 | All dependencies checked for known vulnerabilities | PROPOSED |
| REQ-SEC-004 | Capability promotion to APPROVED requires security review | PROPOSED |
| REQ-SEC-005 | Factory core changes require security impact assessment | PROPOSED |

## Security Gate Reviews

Security gates are embedded at each phase boundary:

1. Threat Model Review -- Before implementation begins.
2. Secure Code Review -- Before code is marked complete.
3. Dependency Scan -- Before any release.
4. Final Security Sign-off -- Before release approval.

## Least Privilege Principle

- Agents operate with minimum necessary permissions.
- Tool adapters scope permissions to specific operations.
- Cross-team writes require explicit approval.
- Production configuration changes require Owner approval.

## Secrets Protection

- No secrets in source code or configuration files.
- Environment variables used for runtime secrets.
- Secret scanning in CI/CD pipeline.
- Regular rotation of any secrets in use.

## Secure Configuration

- Default-deny permission model.
- Configuration as code with version control.
- Security baselines for all environments.
- Regular configuration audits.
