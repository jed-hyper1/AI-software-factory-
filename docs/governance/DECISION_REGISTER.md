# Decision Register

> **Status:** PROPOSED - Subject to owner approval
> **Template:** Each entry records a decision with its rationale and status.

## Decisions

### DEC-001: Project Repository Separation

- **Date:** 2025-01-20
- **Status:** APPROVED (by task definition)
- **Decision:** The Universal AI Software Factory is a separate repository from
  the existing AI-DSS repository. No requirements, implementation, configuration,
  or experimental changes from AI-DSS shall be merged into this repository.
- **Rationale:** The task explicitly states this is an independent side project.
- **Evidence:** Task description Section 3.
- **Consequences:** No shared code or configuration with AI-DSS unless explicitly
  proposed and approved.

### DEC-002: Existing Configuration as Reference Baseline

- **Date:** 2025-01-20
- **Status:** APPROVED (by task definition)
- **Decision:** The existing AI-agent configuration (Codex, DSH, Loop Engineering,
  DDD adversarial review, agent skills) is treated as a reference baseline to be
  assessed, not a permanent constraint to inherit or discard automatically.
- **Rationale:** Task Section 5.
- **Evidence:** [STATUS.md](../../STATUS.md) component assessment.
- **Consequences:** Each component evaluated independently for retain/repair/extend/
  replace/defer.

### DEC-003: 20-Skill Restriction Non-Inheritance

- **Date:** 2025-01-20
- **Status:** PROPOSED
- **Decision:** The 20-skill restriction from the existing setup is NOT automatically
  imposed on this new project. A separate capability governance policy will be
  proposed for owner review.
- **Rationale:** Task Section 5 explicitly states not to automatically impose it.
- **Evidence:** Task Section 5.
- **Consequences:** This project may use more than 20 skills if justified and approved.
- **Next action:** Propose capability governance policy (PENDING).

### DEC-004: License Selection

- **Date:** 2025-01-20
- **Status:** PENDING
- **Decision:** No license has been selected.
- **Rationale:** License selection is a consequential decision requiring owner approval.
- **Evidence:** Task Section 4 states "Do not invent licensing decisions."
- **Next action:** Human Project Owner to select license. REQUIRES OWNER APPROVAL.

### DEC-005: Factory Core vs Project Pack Separation

- **Date:** 2025-01-20
- **Status:** APPROVED
- **Decision:** The factory architecture separates a reusable Factory Core (shared
  infrastructure) from Project Packs (project-specific requirements, rules, and
  acceptance criteria).
- **Rationale:** Task Section 4 requires this separation.
- **Evidence:** [docs/architecture/FACTORY_CORE_AND_PROJECT_PACKS.md](../../docs/architecture/FACTORY_CORE_AND_PROJECT_PACKS.md).

### DEC-006: Documentation-Only Initial Phase

- **Date:** 2025-01-20
- **Status:** APPROVED
- **Decision:** The initial phase establishes and publishes documentation only.
  Implementation is not part of this phase. The next implementation phase requires
  owner approval.
- **Rationale:** Task Section 9: "Do not implement the entire factory merely because
  documentation describes it."
- **Evidence:** [docs/implementation/INITIAL_IMPLEMENTATION_PLAN.md](../../docs/implementation/INITIAL_IMPLEMENTATION_PLAN.md).

### Template for New Decisions

```
### DEC-XXX: [Short Title]

- **Date:** YYYY-MM-DD
- **Status:** [APPROVED | REJECTED | PENDING | PROPOSED | SUPERSEDED]
- **Decision:** [What was decided]
- **Rationale:** [Why this decision]
- **Evidence:** [Links to evidence or references]
- **Consequences:** [What this means for the project]
- **Next action:** [If PENDING, what is needed]
```
