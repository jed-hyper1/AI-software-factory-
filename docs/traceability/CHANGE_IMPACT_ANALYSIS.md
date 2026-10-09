# Change Impact Analysis

> **Status:** PROPOSED

## Purpose

When an artifact changes, determine all affected artifacts across the
traceability graph and assess the impact of the change.

## Impact Analysis Process

### Step 1: Identify the Change

- What artifact is changing?
- What is the nature of the change (additive, modification, deletion)?
- Who proposed the change and why?

### Step 2: Trace Forward

Follow all outgoing links from the changed artifact to find downstream
artifacts that may be affected:

1. Requirements -> Architecture (design may need revision).
2. Architecture -> Implementation (code may need to change).
3. Implementation -> Test (tests may need updating).
4. Test -> Evidence (existing evidence may be invalidated).
5. Evidence -> Release Decision (release criteria may change).

### Step 3: Trace Backward

Follow all incoming links to find upstream artifacts:

- What requirements drove this change?
- What design decisions support it?

### Step 4: Assess Impact

For each affected artifact, assess:

- **Severity:** None / Minor / Major / Critical
- **Effort:** Estimated work to update.
- **Evidence validity:** Whether existing evidence is invalidated.
- **Risk:** Whether the change introduces new risks.

### Step 5: Plan Remediation

- Prioritize affected artifacts by severity and effort.
- Assign teams to update affected artifacts.
- Track updates in the orchestration engine.

## Impact Analysis Template

```
### Change: [Artifact ID and description]

- **Changed by:** [Agent/team]
- **Change type:** [Additive / Modification / Deletion]
- **Affected artifacts:** [List with IDs]
- **Impact assessment:** [Per-artifact severity, effort, evidence]
- **Remediation plan:** [Steps, assignments, timeline]
- **Status:** Proposed / In Progress / Completed
```

## Automated Impact Analysis

The traceability graph enables automated impact analysis:

- Query the graph for all reachable nodes from the changed artifact.
- Flag stale evidence for invalidated artifacts.
- Generate remediation tasks automatically.

## Approval Requirements

- Changes affecting security requirements: Security Team review.
- Changes affecting architecture: Architecture Traceability Team review.
- Changes affecting multiple teams: Factory Lead Agent coordination.
- Changes to factory core: Owner approval.
