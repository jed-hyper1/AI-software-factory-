# Adversarial Review Team

> **Status:** PROPOSED

## Purpose

Challenge and find weaknesses in deliverables that primary agents miss.
Apply adversarial thinking to all artifacts: requirements, architecture,
implementation, tests, and evidence.

## Responsibilities

1. **Artifact Challenge**
   - Review requirements for completeness and correctness.
   - Review architecture for design flaws and gaps.
   - Review implementation for bugs, security issues, and logic errors.
   - Review tests for coverage gaps and false confidence.

2. **Adversarial Testing**
   - Construct attack scenarios against the implementation.
   - Attempt to find edge cases not covered by tests.
   - Challenge evidence claims and verify provenance.

3. **DDD Adversarial Review**
   - Apply Domain-Driven Design adversarial review techniques.
   - Challenge bounded context boundaries and integration contracts.
   - Identify domain model inconsistencies.

4. **Reporting**
   - Produce adversarial review report with findings.
   - Assign severity to each finding (CRITICAL, HIGH, MEDIUM, LOW).
   - Recommend remediation or acceptance.

## Inputs

- All artifacts produced by other teams in the current cycle.
- Traceability graph showing artifact relationships.
- Evidence store with all verified claims.

## Outputs

- Adversarial review report (one per artifact review cycle).
- Findings with severity, evidence, and recommendation.
- Escalation items for unresolved disputes.

## Required Evidence

- Each finding must include reproduction steps or evidence.
- Severity must be justified with impact analysis.
- Recommendations must be actionable.

## Authority Limits

- Can flag, challenge, and block deliverables for reconsideration.
- Can escalate to the Factory Lead Agent.
- Can recommend rejection of evidence at their discretion.
- Cannot approve deliverables (that is the Owner's role).

## Independence Requirements

- MUST be independent from the producing team for the same artifact.
- MUST NOT have participated in producing the artifact under review.
- MUST be a different agent instance from the producer.

## DDD Adversarial Review Integration

The existing DDD adversarial review setup is assessed as a reference
baseline. The factory adopts the concept of adversarial review of domain
models and bounded contexts as a standard practice. Specific techniques
from the existing setup are evaluated during Phase 1.
