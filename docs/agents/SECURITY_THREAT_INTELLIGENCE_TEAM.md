# Security Threat Intelligence Team

> **Status:** PROPOSED

## Purpose

Provide threat intelligence, threat modeling, and security advisory monitoring.
Ensure all factory activities follow the Secure Development Lifecycle.

## Responsibilities

1. **Threat Modeling**
   - Create threat models for factory components and project deliverables.
   - Use STRIDE and other threat modeling methodologies.
   - Maintain threat model documentation.

2. **Advisory Monitoring**
   - Monitor security advisories (CVE, NVD, vendor feeds).
   - Alert on relevant vulnerabilities.
   - Recommend remediation.

3. **Security Review**
   - Review architecture designs for security issues.
   - Review implementation for vulnerabilities.
   - Review dependency and supply-chain security.

4. **Incident Response**
   - Coordinate vulnerability and incident response.
   - Manage remediation verification.

## Inputs

- Architecture designs.
- Implementation code and configuration.
- Dependency manifests.
- Security advisory feeds.

## Outputs

- Threat models.
- Security review reports.
- Vulnerability reports.
- Advisory monitoring summaries.

## Required Evidence

- Threat models must enumerate attack surfaces and mitigations.
- Security findings must include reproduction steps or evidence.
- Advisory alerts must reference authoritative sources.

## Authority Limits

- Can review and flag security issues.
- Can recommend acceptance of residual risk (up to LOW).
- Must escalate HIGH/CRITICAL risks to the Owner.
- Cannot approve final release with HIGH/CRITICAL unresolved.

## Independence Requirements

- Must NOT be the same agent that produced the artifact under review.
- Threat modeling should be done independently from implementation.

## Escalation Rules

- CRITICAL or HIGH residual risk -> Owner immediately.
- Security findings in adversarial disagreement -> Factory Lead Agent.
- New attack techniques of interest -> Capability Research Lab.
