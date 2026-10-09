# Validation Strategy

> **Status:** PROPOSED

## Purpose

Define how the factory validates that it works. Separate planned tests from
tests actually executed and passed.

## Validation Principles

1. Evidence-first. Validation produces evidence, not just assertions.
2. Independent verification. The team that builds must not be the sole
   team that tests.
3. Reproducible. Tests must be re-runnable with deterministic setup.
4. Measurable. Acceptance criteria are measurable and testable.
5. Adversarial. Adversarial review challenges all validation claims.

## Validation Layers

| Layer | Scope | Responsible Team |
|---|---|---|
| Unit | Individual functions, tools, skills | Delivery Engineering |
| Integration | Team-to-team artifact flow | Architecture Traceability |
| System | End-to-end factory workflow | Independent Verification |
| Adversarial | Challenge all deliverables | Adversarial Review Team |
| Security | Security-specific validation | Security Threat Intelligence |

## Planned Tests (PENDING Implementation)

The following tests are planned but NOT yet executed:

| Test ID | Layer | Description | Status |
|---|---|---|---|
| VAL-001 | System | End-to-end: requirements discovery to release | PLANNED |
| VAL-002 | Integration | Traceability link completeness | PLANNED |
| VAL-003 | System | Phase gate transition | PLANNED |
| VAL-004 | Adversarial | Evidence tampering resistance | PLANNED |
| VAL-005 | Security | Threat model coverage | PLANNED |
| VAL-006 | System | Capability adoption lifecycle | PLANNED |

## Executed Tests (None Yet)

No tests have been executed yet. This will be updated as tests run.

| Test ID | Layer | Executed Date | Result | Evidence |
|---|---|---|---|---|
| (none) | | | | |

## Validation Gates

Validation gates are checkpoints where validation evidence must be presented:

1. Discovery Gate: Requirements discovery tests pass.
2. Design Gate: Architecture and traceability validation passes.
3. Build Gate: Implementation and unit tests pass.
4. Test Gate: Integration and system tests pass.
5. Review Gate: Adversarial and security reviews complete.
6. Release Gate: Final validation and Owner approval.
