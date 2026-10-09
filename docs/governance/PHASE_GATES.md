# Phase Gates

> **Status:** PROPOSED - Subject to owner approval

## Overview

Phase gates are approval checkpoints that must pass before the factory can
transition from one phase to the next. Each gate has explicit entry criteria,
verification requirements, required evidence, and required approvers.

## Gate Definitions

### Gate 0: Foundation Complete

- **From Phase:** P0 Foundation
- **To Phase:** P1 Reference Baseline
- **Entry criteria:** All required documentation published.
- **Verification:** Internal link validation, cross-reference consistency.
- **Required evidence:** Validation report, file inventory.
- **Approver:** Human Project Owner.
- **Status:** NOT_YET_APPLICABLE

### Gate 1: Baseline Assessment

- **From Phase:** P1 Reference Baseline
- **To Phase:** P2 Pilot Implementation
- **Entry criteria:** All existing components assessed with evidence;
  capability gaps catalogued.
- **Verification:** Assessment matrix, gap analysis, recommendation summary.
- **Required evidence:** STATUS.md updated, capability registry draft.
- **Approver:** Human Project Owner.
- **Status:** NOT_YET_APPLICABLE

### Gate 2: Pilot Ready

- **From Phase:** P2 Pilot Implementation
- **To Phase:** P3 Scaling & Automation
- **Entry criteria:** Pilot project completed end-to-end with full
  traceability, evidence, and gate validation.
- **Verification:** Traceability audit, evidence completeness check,
  adversarial review sign-off.
- **Required evidence:** Pilot completion report, traceability matrix.
- **Approver:** Human Project Owner.
- **Status:** NOT_YET_APPLICABLE

### Gate 3: Production Ready

- **From Phase:** P3 Scaling & Automation
- **To Phase:** P4 Self-Improvement (Production)
- **Entry criteria:** Multiple project packs supported;
  automation operational; research process running.
- **Verification:** Multi-pack validation, automation coverage,
  research cadence demonstrated.
- **Required evidence:** Scaling report, automation inventory,
  research process documentation.
- **Approver:** Human Project Owner.
- **Status:** NOT_YET_APPLICABLE

### Gate 4: Continuous Improvement

- **From Phase:** P4 Self-Improvement
- **Continuity:** Ongoing (no end phase)
- **Entry criteria:** Factory demonstrates evidence-backed self-improvement.
- **Verification:** Improvement experiment log, capability lifecycle operational.
- **Required evidence:** Improvement report, lifecycle metrics.
- **Approver:** Human Project Owner (annual review).
- **Status:** NOT_YET_APPLICABLE

## Gate Review Process

1. Pre-gate: Compile evidence package and traceability matrix.
2. Adversarial review: Independent team challenges the evidence.
3. Gate review: Designated approver evaluates against entry criteria.
4. Decision: Approve, reject with remediation, or request more evidence.
5. Record: Decision logged in DECISION_REGISTER.md.

## Gate Failure Handling

- If a gate fails, the factory returns to the preceding phase.
- Remediation plan must be submitted and approved before re-attempting.
- Root cause analysis is required for any gate failure.
