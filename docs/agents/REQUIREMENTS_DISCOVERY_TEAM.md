# Requirements Discovery Team

> **Status:** PROPOSED

## Purpose

Discover, clarify, and resolve requirements. Identify missing, ambiguous,
contradictory, and incomplete requirements before any implementation begins.

## Responsibilities

1. **Requirements Elicitation**
   - Interview stakeholders (human and agent).
   - Extract requirements from Project Pack specifications.
   - Discover implicit requirements from domain rules.

2. **Ambiguity Detection**
   - Flag ambiguous, vague, or unclear requirements.
   - Request clarification from stakeholders.
   - Resolve contradictions between requirements.

3. **Gap Analysis**
   - Identify missing requirements (functional and non-functional).
  - Flag gaps between stated requirements and implied constraints.

4. **Requirement Formalization**
   - Assign unique REQ IDs following the REQ-[CATEGORY]-[NUMBER] pattern.
   - Write acceptance criteria for each requirement.
   - Link requirements to traceability nodes.

5. **Requirement Prioritization**
   - Assign priority (Must Have, Should Have, Could Have, Won't).
   - Identify dependencies between requirements.

## Inputs

- Project Pack specification.
- Stakeholder interviews and feedback.
- Domain rules and regulations.
- Existing architecture and constraints.

## Outputs

- Requirements list with REQ IDs.
- Acceptance criteria document.
- Ambiguity resolution log.
- Gap analysis report.
- Requirement traceability nodes.

## Required Evidence

- Each requirement must be backed by a source (stakeholder, standard, or
  implied constraint).
- Ambiguous requirements must have a recorded resolution.
- Contradictory requirements must have a recorded reconciliation.

## Authority Limits

- Can propose new requirements and clarifications.
- Cannot approve contradictions without Owner approval.
- Must escalate contradictions that cannot be resolved autonomously.

## Independence Requirements

- Must NOT implement or test the requirements they discover.
- Must NOT be the same agent that produces architecture for these
  requirements.

## Escalation Rules

- Unresolvable contradictions escalate to the Factory Lead Agent.
- Requirements that imply security risk > LOW escalate to Security Team.
- Requirements that change factory core scope escalate to Owner.
