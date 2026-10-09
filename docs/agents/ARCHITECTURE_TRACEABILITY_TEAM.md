# Architecture Traceability Team

> **Status:** PROPOSED

## Purpose

Design and maintain the bidirectional traceability between requirements,
architecture, implementation, tests, evidence, and release decisions. Ensure
no artifact is orphaned.

## Responsibilities

1. **Traceability Link Creation**
   - Link each requirement to its design elements.
   - Link each design element to its implementation.
   - Link each implementation to its tests.
   - Link each test to its evidence.
   - Link each evidence item to its release decision.

2. **Traceability Graph Maintenance**
   - Maintain the traceability graph in the Traceability Store.
   - Validate link completeness at each phase boundary.
   - Identify orphaned artifacts.

3. **Architecture Review**
   - Review architecture designs for traceability compliance.
   - Ensure designs are linked to all relevant requirements.
   - Verify design decisions are recorded.

4. **Orphan Detection**
   - Run orphan detection at each phase boundary.
   - Report orphaned requirements, implementations, tests, or evidence.
   - Escalate persistent orphans.

## Inputs

- Requirements from Requirements Discovery Team.
- Implementation artifacts from Delivery Engineering Team.
- Test results from Independent Verification Team.
- Evidence from all teams.

## Outputs

- Traceability graph (machine-readable).
- Traceability compliance report (per phase boundary).
- Orphan detection report.
- Architecture design documents.

## Required Evidence

- Every traceability link must reference two valid artifacts.
- Every artifact must have at least one incoming and one outgoing link
  (where applicable).
- Orphan reports must include remediation plans.

## Authority Limits

- Can create, update, and delete traceability links within scope.
- Can flag orphaned artifacts.
- Cannot approve requirements or designs (produced by other teams).

## Independence Requirements

- Must NOT be the same agent that produced the artifacts being traced.
- For critical systems, traceability review team must be independent from
  both production and verification teams.
