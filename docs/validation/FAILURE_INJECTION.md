# Failure Injection

> **Status:** PROPOSED

## Purpose

Proactively test how the factory handles failures by injecting faults
and verifying recovery behavior.

## Failure Injection Targets

| Target | Injected Failure | Expected Recovery | Status |
|---|---|---|---|
| Agent process | Kill agent mid-task | Reassign to another agent, restore from checkpoint | PLANNED |
| Evidence store | Simulate corruption | Checksum detection, immutable restore | PLANNED |
| Model provider | API timeout/unavailable | Fail over to alternate adapter | PLANNED |
| Traceability store | Lost links | Rebuild from version control | PLANNED |
| Network | Simulate partition | Graceful degradation, retry | PLANNED |
| Memory | Simulate context overflow | Context compression, offload to store | PLANNED |

## Injection Methods

### 1. Agent Crash Simulation

- Terminate agent process during task execution.
- Verify checkpoint restoration.
- Verify task reassignment.

### 2. Evidence Corruption

- Modify an evidence record in the store.
- Verify checksum detection.
- Verify immutable restore from backup.

### 3. Capability Failure

- Fail a model provider API.
- Verify failover to alternate adapter.
- Verify task completion with fallback.

## Recovery Validation

Each failure injection must produce:

- Detection time (how quickly the failure was detected).
- Recovery time (how quickly the system recovered).
- Data integrity verification (no data loss).
- Evidence of recovery steps taken.

## Failure Injection Schedule

- PLANNED: Run after Phase 2 (Pilot Implementation).
- Frequency: Monthly after factory is operational.
