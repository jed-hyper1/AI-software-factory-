# Capability Adoption Lifecycle

> **Status:** PROPOSED

## Overview

Capabilities (models, frameworks, tools, skills, methods) progress through a
defined lifecycle before they may be used in trusted factory configuration.

## Lifecycle Stages

```
DISCOVERED
    |
    v
SCREENED  (basic viability, license, security check)
    |
    v
EXPERIMENTAL  (limited use in sandboxed/non-trusted contexts)
    |
    v
BENCHMARKED  (evaluated against standardized benchmarks)
    |
    v
APPROVED  (Owner approves for trusted use)
    |
    v
ACTIVE  (in regular use in factory configuration)
    |
    v
DEPRECATED  (superseded or no longer recommended)
```

## Stage Criteria

| Stage | Entry Criteria | Exit Criteria |
|---|---|---|
| DISCOVERED | Capability identified, basic info recorded | Pass initial screening checklist |
| SCREENED | License compatible, no known critical vulnerabilities, actively maintained | Pass security pre-check, basic functionality verified |
| EXPERIMENTAL | PASS screening, Owner-granted sandbox access | Demonstrate utility in sandbox, pass basic tests |
| BENCHMARKED | PASS experimental, reproducible benchmark designed | Benchmark completed with results recorded |
| APPROVED | PASS benchmarking, security review passed, cost acceptable | Owner approval granted |
| ACTIVE | APPROVED, integrated into factory configuration | In active use, monitoring ongoing |
| DEPRECATED | Superseded by newer capability or no longer maintained | Not used in new projects; migration path defined |

## Stage Transitions

### DISCOVERED -> SCREENED

Performed by: Capability Research Lab
Required: License check, vulnerability scan, maintenance status verification.
Approval: Team Lead (no Owner approval needed).

### SCREENED -> EXPERIMENTAL

Performed by: Capability Research Lab
Required: Basic functionality test, security pre-check.
Approval: Factory Lead Agent (sandbox access grant).

### EXPERIMENTAL -> BENCHMARKED

Performed by: Capability Research Lab
Required: Benchmark design and execution, results analysis.
Approval: Capability Research Lab Lead.

### BENCHMARKED -> APPROVED

Performed by: Capability Research Lab
Required: Security review, cost analysis, Owner presentation.
Approval: **Human Project Owner REQUIRED.**

### APPROVED -> ACTIVE

Performed by: Factory Lead Agent
Required: Integration into factory configuration, deployment.
Approval: **Human Project Owner REQUIRED.**

### ACTIVE -> DEPRECATED

Performed by: Capability Research Lab
Required: Evidence of obsolescence or issues.
Approval: Factory Lead Agent + Owner notification.

## Rejected Candidates

Rejected candidates remain in the registry with:

- Reason for rejection (security, cost, performance, etc.).
- Date of rejection.
- Any re-evaluation notes.

## Capability Governance for New Project

> **Status:** PROPOSED - Not yet approved

This project does NOT inherit the 20-skill restriction from the existing
AI-DSS setup. Instead, the capability lifecycle above governs capability
adoption. The Owner may impose limits at any stage via the approval policy.
