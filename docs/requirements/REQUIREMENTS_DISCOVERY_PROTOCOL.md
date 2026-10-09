# Requirements Discovery Protocol

> **Status:** PROPOSED

## Purpose

Standardize how the Requirements Discovery Team elicits, identifies,
documents, and resolves requirements. Ensure ambiguity, contradiction, and
incompleteness are detected before implementation.

## Requirement ID Format

```
REQ-[CATEGORY]-[NUMBER]
```

### Categories

| Category | Meaning |
|---|---|
| FUNC | Functional requirement |
| NONFUNC | Non-functional requirement |
| SEC | Security requirement |
| PERF | Performance requirement |
| COMPAT | Compatibility requirement |
| REG | Regulatory or compliance requirement |
| DOM | Domain rule |

### Examples

- REQ-FUNC-001 -- User can create a new project pack.
- REQ-SEC-015 -- All evidence records must be immutable.
- REQ-NONFUNC-003 -- Factory must recover from agent crash within 30s.

## Discovery Process

### Step 1: Stakeholder Elicitation

1. Identify stakeholders (human, agent, system).
2. Conduct interviews or review existing specifications.
3. Extract raw requirements without filtering.

### Step 2: Requirement Parsing

1. Assign REQ IDs to each raw requirement.
2. Categorize each requirement.
3. Identify prerequisite requirements.

### Step 3: Ambiguity Detection

For each requirement, check:

- Is the language precise and unambiguous?
- Are success and failure criteria defined?
- Are units, thresholds, and conditions specified?

Flag ambiguous requirements for clarification.

### Step 4: Contradiction Detection

- Compare requirements within the same category.
- Compare functional vs. non-functional requirements.
- Use dependency graph to detect conflicts.

Flag contradictory requirements for resolution.

### Step 5: Completeness Check

- Verify all functional requirements have corresponding non-functional
  requirements (performance, security, usability).
- Check for missing requirements in standard categories.
- Validate against Project Pack specifications.

### Step 6: Resolution

- Clarify ambiguous requirements with stakeholders.
- Resolve contradictions with stakeholders.
- Document all resolutions in the Ambiguity Resolution Log.

## Ambiguity Resolution Log

Each entry in the ambiguity resolution log includes:

- Requirement ID.
- Original ambiguous text.
- Clarification requested.
- Resolution provided.
- Resolution source (stakeholder name or reference).
- Resolution date.

## Requirement Documentation Format

```
### REQ-FUNC-001: [Short Title]

- **Source:** [Stakeholder or reference]
- **Description:** [Clear, unambiguous description]
- **Acceptance Criteria:** [Link to ACCEPTANCE_CRITERIA.md]
- **Priority:** Must/Should/Could/Won
- **Status:** Approved / Pending / Proposed
- **Related Requirements:** [REQ-XXX, REQ-YYY]
```

## Discovery Evidence

Every discovered requirement must include:

- A source (stakeholder interview, specification, standard, etc.).
- A traceability link to the source.
- An ambiguity or contradiction flag (if applicable).
