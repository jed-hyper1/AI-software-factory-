# Threat Modeling

> **Status:** PROPOSED

## Purpose

Identify, enumerate, and mitigate security threats to the Universal AI
Software Factory and its outputs.

## Threat Modeling Methodology

This factory uses STRIDE as the primary threat modeling methodology,
supplemented by attack tree analysis for high-severity threats.

### STRIDE Categories

| Category | Description | Example in Factory Context |
|---|---|---|
| Spoofing | Impersonating another entity | Agent impersonating another team |
| Tampering | Unauthorized modification of data | Evidence record modification |
| Repudiation | Refusing to perform an action | Agent denying it produced evidence |
| Information Disclosure | Exposing sensitive data | Leaking requirements to unauthorized parties |
| Denial of Service | Making system unavailable | Resource exhaustion during agent execution |
| Elevation of Privilege | Escalating to higher privileges | Agent exceeding its authority limits |

## Threat Model: Factory Core

### Assets

1. Evidence Store (immutable but critical).
2. Traceability Graph.
3. Agent authorization and permission configuration.
4. Model provider API keys (if applicable).
5. Human Project Owner decisions and approvals.

### Trust Boundaries

```
+------------------------------------------------+
|                    Owner                      |
|         (highest trust, all authority)        |
+---------+-------------------+------------------+
|  Factory  |   Agent Teams   |  Research/Lab   |
|   Core    |  (standard trust)|  (lowest trust)  |
+---------+--------+----------+------------------+
|  L2: Agent Harness (Model/API adapters)      |
+---------+----------+---------+-----------------+
|  L1: Infrastructure (Storage, Compute)       |
+------------------------------------------------+
```

### Threats

| ID | STRIDE | Threat | Mitigation | Status |
|---|---|---|---|---|
| T-001 | Tampering | Evidence record modification | Immutable store, checksums, append-only | PROPOSED |
| T-002 | Elevation of Privilege | Agent exceeding authority | Authority model, permission checks | PROPOSED |
| T-003 | Information Disclosure | Requirements leaked to unauthorized parties | Prompt sanitization, no raw secrets to models | PROPOSED |
| T-004 | Spoofing | Agent impersonating another team | Agent identity verification, signed evidence | PROPOSED |
| T-005 | Denial of Service | Resource exhaustion during agent execution | Budget limits, concurrency control | PROPOSED |
| T-006 | Information Disclosure | Model training on proprietary data | No proprietary data sent to third-party models without approval | PROPOSED |

## Threat Model: Project Deliverable

Each project pack must produce a project-specific threat model. The Security
Threat Intelligence Team leads this, with input from all teams.

## Attack Tree Example: Evidence Tampering

```
Goal: Tamper with evidence records
  |
  +--- Access Evidence Store directly
  |     +--- Compromise storage credentials
  |     +--- Exploit storage vulnerability
  |
  +--- Submit false evidence as an agent
        +--- Agent exceeds authority
        +--- Adversarial review fails
        +--- Verification team is compromised
```

Mitigation: Immutable append-only store with checksums,
independent verification, and authority model enforcement.
