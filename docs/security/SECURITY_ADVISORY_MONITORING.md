# Security Advisory Monitoring

> **Status:** PROPOSED

## Purpose

Monitor relevant security advisories, emerging attack techniques,
vulnerabilities, and defensive practices.

## Advisory Sources

| Source | Type | Frequency | Reliability |
|---|---|---|---|
| CVE / NVD | Vulnerability database | Daily | High |
| OWASP | Best practices, Top 10 | Weekly | High |
| GitHub Security Advisories | Dependency vulnerabilities | Daily | High |
| Model provider security bulletins | Model/API security | Weekly | Medium |
| Agent framework security notices | Framework vulnerabilities | Weekly | Medium |
| SANS Internet Storm Center | Threat intelligence | Daily | High |
| MITRE ATT&CK | Attack technique catalog | Monthly | High |
| Security vendor feeds | Emerging threats | Daily | Variable |

## Monitoring Process

### Step 1: Collection

- Subscribe to advisory feeds for all components in the capability registry.
- Monitor for announcements about models, frameworks, tools, and skills.
- Monitor for new attack techniques relevant to AI agents.

### Step 2: Triage

- Assess relevance to the factory.
- Assign severity (CRITICAL, HIGH, MEDIUM, LOW).
- Check if affected components are in use.

### Step 3: Alerting

- CRITICAL and HIGH: immediate alert to Security Team and Owner.
- MEDIUM: daily summary report.
- LOW: weekly summary report.

### Step 4: Response

- See [docs/security/INCIDENT_AND_VULNERABILITY_RESPONSE.md](INCIDENT_AND_VULNERABILITY_RESPONSE.md) for the response process.

## Relevance Criteria

An advisory is relevant if it affects:

1. Models, frameworks, or tools in the capability registry.
2. Dependencies of project packs.
3. The factory core infrastructure.
4. Agent skills in active use.

## Source Dates and Applicability

All advisory entries record:

- Source URL and publication date.
- Applicable components and versions.
- Assessment of applicability to the factory.
- Action taken or recommended.

## Do Not Claim Complete Security

This monitoring system does NOT guarantee complete threat detection.
New vulnerabilities and zero-days may exist that are not yet known to any
feed. Independent security assessment is always recommended.
