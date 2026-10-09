# Failure Recovery

> **Status:** PROPOSED

## Overview

The factory must handle agent failures, evidence corruption, lost state,
and partial completions gracefully. This document defines recovery patterns.

## Failure Modes

| Failure Mode | Description | Recovery Strategy |
|---|---|---|
| Agent crash | Agent process terminates unexpectedly | Reassign task to another agent; restore state from last checkpoint |
| Evidence corruption | Evidence record modified or lost | Immutable evidence store; detect via checksums; restore from backup |
| Lost state | Workflow state lost | Restore from last persisted state; replay from evidence store |
| Partial completion | Task partially done but not committed | Review evidence; decide continue, revert, or restart |
| Adversarial disagreement | Adversarial team and primary team disagree | Escalate to Factory Lead Agent; Owner decision if unresolved |
| Capability failure | Tool or model provider unavailable | Fail over to alternate adapter; flag for research team |
| Deadlock | Teams blocked waiting on each other | Factory Lead Agent intervenes; may skip, prioritize, or reassign |

## Checkpoint Strategy

State is checkpointed at:

1. Phase boundaries (after each phase gate).
2. Evidence submission points (after each team delivers evidence).
3. Time-based intervals (every N minutes of agent work).

## Rollback Strategy

- Traceability links enable identifying all artifacts affected by a decision.
- Evidence immutability prevents false evidence from being accepted.
- Version-controlled requirements and architecture allow rollback to known
  good states.

## Evidence Integrity

- Evidence Store is append-only (immutable).
- Each evidence record includes a checksum.
- Checksums are verified before evidence is accepted.
- Tampering is detected and the evidence is flagged.

## Recovery Process

1. Detect -- Identify the failure mode and scope.
2. Assess -- Determine what state and evidence are lost or corrupted.
3. Restore -- Recover state from the last good checkpoint.
4. Reassign -- Reassign affected tasks to available agents.
5. Verify -- Independent Verification Team validates recovery.
6. Resume -- Resume work, with the Factory Lead Agent monitoring.
7. Document -- Record the failure and recovery in the risk register.
