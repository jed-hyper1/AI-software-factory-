# Acceptance Criteria

> **Status:** PROPOSED

## Purpose

Define how acceptance criteria are written, linked to requirements, and
verified. Each requirement must have associated acceptance criteria.

## Acceptance Criteria Format

```
### AC-[REQ-ID]-[NUMBER]: [Short Description]

- **Requirement:** REQ-[CATEGORY]-[NUMBER]
- **Given:** [Preconditions]
- **When:** [Action or trigger]
- **Then:** [Expected outcome]
- **Evidence Required:** [What evidence must be produced]
- **Status:** Proposed / Approved
```

## Writing Good Acceptance Criteria

1. **Independent** -- Each criterion should be independently testable.
2. **Negotiable** -- Not a contract; allows for alternative implementations.
3. **Valuable** -- Each criterion delivers value through behavior.
4. **Estimable** -- Can be scoped and effort-estimated.
5. **Small** -- Small enough to implement and verify quickly.
6. **Testable** -- Has a clear pass/fail condition.

## Acceptance Criteria Status

| Status | Meaning |
|---|---|
| Proposed | Drafted by Requirements Discovery Team |
| Approved | Reviewed and accepted by stakeholders |
| Verified | Evidence produced and accepted by Independent Verification Team |
| Rejected | Not accepted; requires revision |

## Linking to Requirements

Each acceptance criterion links to exactly one requirement (REQ ID).
Each requirement may have multiple acceptance criteria.

## Acceptance Criteria for Factory Core Requirements

| Requirement | Acceptance Criteria | Evidence |
|---|---|---|
| REQ-SEC-001 (Evidence immutability) | Evidence Store rejects modification | Test report |
| REQ-NONFUNC-001 (Crash recovery) | Agent crash recovers within 30s | Test report |
| REQ-FUNC-001 (REQ ID generation) | New requirements get unique IDs | Evidence log |

## Factory-Level Acceptance

A factory phase is accepted when:

1. All requirements for the phase have acceptance criteria.
2. All acceptance criteria have verified evidence.
3. Adversarial review has no outstanding CRITICAL or HIGH findings.
4. Security review has no outstanding CRITICAL or HIGH findings.
5. Phase gate has been approved by the Owner.
