# Bidirectional Traceability Model

> **Status:** PROPOSED

## Purpose

Define how artifacts are linked bidirectionally so that changing any artifact
reveals all affected artifacts upstream and downstream.

## Artifact Types

| Type | Code | Description |
|---|---|---|
| Requirement | REQ | Discovered requirement with REQ ID |
| Architecture | ARCH | Design decision or component specification |
| Implementation | IMPL | Code, configuration, or build artifact |
| Test | TEST | Test case or test run |
| Evidence | EVID | Verification evidence (pass/fail, metrics) |
| Release Decision | REL | Decision to release, with rationale |

## Traceability Link Format

```
TR-[SOURCE]-[TARGET]-[INDEX]
```

### Example

TR-REQ001-ARCH001-1 links Requirement REQ-FUNC-001 to Architecture ARCH-FUNC-001.

## Link Directionality

Every link is bidirectional:

- **Forward (upstream to downstream):** Requirement to Architecture,
  Architecture to Implementation, Implementation to Test, Test to Evidence,
  Evidence to Release Decision.

- **Backward (downstream to upstream):** Each link allows traversal in
  both directions.

## Link Validation Rules

1. Every requirement must link to at least one architecture element.
2. Every architecture element must link to at least one implementation.
3. Every implementation must link to at least one test.
4. Every test must link to at least one evidence item.
5. Every evidence item must link to a release decision (if applicable).
6. No circular links (A links to B and B links to A is only valid if they
   are the same link traversed in opposite directions).

## Orphan Detection

The Architecture Traceability Team runs orphan detection at each phase boundary.
Orphans are artifacts not linked to any other artifact.

### Orphan Types

| Orphans To Find | Query |
|---|---|
| Unlinked Requirements | REQ nodes with no ARCH outgoing link |
| Unlinked Architecture | ARCH nodes with no IMPL outgoing link |
| Unlinked Implementation | IMPL nodes with no TEST outgoing link |
| Unlinked Tests | TEST nodes with no EVID outgoing link |
| Unlinked Evidence | EVID nodes with no REL link (if applicable) |

## Traceability Store

Links are stored in a graph database or structured file format. Each link
includes metadata:

- Source artifact ID.
- Target artifact ID.
- Link type (e.g., derives-from, refines, implements, tests, verifies).
- Created by (agent or team).
- Created timestamp.
- Justification or rationale.

## Traceability Compliance

At each phase gate, a traceability compliance report is generated showing:

- Total artifacts per type.
- Total links per type.
- Number of orphans.
- Coverage percentages (requirements with architecture, etc.).
