# Dependency and Supply Chain Security

> **Status:** PROPOSED

## Purpose

Ensure the security and integrity of all dependencies and the supply chain
for both the factory core and project deliverables.

## Dependency Management

### Principles

1. All dependencies must be declared and version-pinned.
2. Dependencies must be scanned for known vulnerabilities on every build.
3. Dependencies must be from trusted sources (verified publishers).
4. Transitive dependencies must be traceable.

### Scanning Tools

| Tool | Scope | Integration |
|---|---|---|
| pip-audit / npm audit | Language-specific | CI/CD pipeline |
| Snyk / Dependabot | Multi-language | CI/CD pipeline |
| SBOM generation | Full dependency graph | Pre-release |

## Supply Chain Security

### Threats

- Typosquatting packages.
- Compromised package repositories.
- Dependency confusion attacks.
- Malicious agent skills.

### Mitigations

- Use trusted registries only (PyPI, npmjs.org, etc.).
- Enable two-factor authentication on all package publisher accounts.
- Review and audit agent skills before adoption
  (see docs/research/[docs/research/CAPABILITY_ADOPTION_LIFECYCLE.md](../research/CAPABILITY_ADOPTION_LIFECYCLE.md)).
- Generate and verify SBOMs for all releases.
- Pin dependencies to specific versions.
- Monitor for dependency confusion
  (private package names on public registries).

## Agent Skill Supply Chain

Agent skills are evaluated through the capability adoption lifecycle:

1. Initial screening for malicious patterns or obfuscated payloads.
2. Security audit by the Security Threat Intelligence Team.
3. Sandbox testing in EXPERIMENTAL stage.
4. Security review before promotion to APPROVED.

See docs/research/[docs/research/CAPABILITY_ADOPTION_LIFECYCLE.md](../research/CAPABILITY_ADOPTION_LIFECYCLE.md) for details.

## Verification

- Dependency scans must pass before any release.
- SBOM must be generated and stored with release artifacts.
- Supply chain audits are conducted quarterly.
