# Black-Box Simulation Plan

**Date:** 2026-10-09
**Status:** PROPOSED

## 1. System Under Test

The Universal AI Software Factory (documentation foundation) as a project
coordination and requirement-discovery framework. The system under test is the
factory's ability to identify missing, ambiguous, contradictory, and incomplete
requirements when given a specification input.

## 2. User-Visible Entry Points

1. Requirements discovery protocol (docs/requirements/REQUIREMENTS_DISCOVERY_PROTOCOL.md)
2. Agent team model (docs/agents/AGENT_TEAM_MODEL.md)
3. Bidirectional traceability (docs/traceability/BIDIRECTIONAL_TRACEABILITY_MODEL.md)
4. Adversarial review (docs/agents/ADVERSARIAL_REVIEW_TEAM.md)

## 3. Expected Behaviors and Outputs

Given a software project specification, the factory should:
- Identify missing requirements (gaps)
- Identify ambiguous requirements (clarification needed)
- Identify contradictory requirements (conflicts)
- Produce a traceability matrix linking requirements to architecture and tests
- Surface security threats via STRIDE threat modeling
- Generate a prioritized findings report

## 4. Test Scenarios

| ID | Scenario | Input | Expected Output | Type |
||--|--|--|--|
| SIM-01 | Simple spec | Basic app spec | All requirements identified | Normal |
| SIM-02 | Ambiguous spec | Vague requirements | Ambiguity flags raised | Negative |
| SIM-03 | Contradictory spec | Conflicting reqs | Contradiction detected | Negative |
| SIM-04 | Missing context | Partial spec | Gaps identified | Boundary |
| SIM-05 | Security-sensitive | Auth flow | STRIDE threats listed | Adversarial |
| SIM-06 | Cross-team handoff | Multi-team spec | Traceability maintained | Integration |

## 5. Simulation Approach

Phase 1: Manual specification analysis using the factory's documented
requirements discovery protocol as a black-box method.

Phase 2: Tool-assisted analysis using DSH to run agent teams (when API
credentials are available).

Phase 3: CLI-Anything integration (when installed) to control test
applications for requirement validation.

---

## Evidence Management

All simulation runs will be recorded with:
- Run identifier and timestamp
- Input specification hash
- Agent configuration version
- Raw outputs and error logs
- Reviewer verdicts
- Known limitations