# Authority Model

> **Status:** PROPOSED - Subject to owner approval

## Purpose

This document defines who (or what) has authority over what decisions in the
Universal AI Software Factory, and at what level of review.

## Key Roles

| Role | Description | Authority |
|---|---|---|
| Human Project Owner | The person who owns this side project. Final authority over governance, consequential decisions, and risk acceptance. | Ultimate authority. Can delegate, override, or reject any agent decision. |
| Factory Lead Agent | The top-level orchestrator that coordinates agent teams. | Execute within approved boundaries. Cannot change governance or autonomy scope without approval. |
| Agent Team | A logical role with defined responsibilities, inputs, outputs, and evidence requirements. | Execute assigned tasks within their domain and authority limits. |
| Adversarial Reviewer | An independent agent or team that challenges primary agents output. | Can flag, escalate, or block deliverables for reconsideration. |
| Research Agent | An agent or team that evaluates AI models, tools, and capabilities. | Recommend capability adoption or rejection. Cannot promote to trusted configuration without approval. |

## Authority Hierarchy

1. **Human Project Owner** (top-level)
   - Governance changes
   - Licensing decisions
   - Phase gate approvals
   - Risk acceptance for residual security issues
   - Autonomy boundary changes
   - Final release approval

2. **Factory Lead Agent** (delegated)
   - Project pack selection and configuration
   - Phase transitions (with gate approval)
   - Capability adoption recommendations (requires owner sign-off for APPROVED status)

3. **Agent Teams** (specialized)
   - Domain-specific execution within their scope
   - Evidence collection and validation
   - Internal quality checks

4. **Adversarial Reviewers** (independent)
   - Challenge and verify deliverables
   - Escalate issues
   - Block deliverables with critical concerns

## Decision Authority Matrix

| Decision Type | Who Can Decide | Requires Owner Approval |
|---|---|---|
| New requirement | Requirements Discovery Team | If PENDING > 5 items or contradicts existing REQ |
| Architecture design | Architecture Traceability Team | If affects factory core (non-project-pack) |
| Code implementation | Delivery Engineering Team | No |
| Test design | Independent Verification Team | No |
   Test execution | Independent Verification Team | No |
| Security threat model | Security Threat Intelligence Team | If residual risk > LOW |
| Security remediation | Delivery Engineering Team | If residual risk > LOW (escalated) |
| Capability adoption (DISCOVERED to SCREENED) | Capability Research Lab | No |
| Capability promotion to APPROVED | Research Agent + Owner | YES |
| Capability promotion to ACTIVE | Owner | YES |
| Factory governance change | Owner only | YES |
| Autonomy boundary change | Owner only | YES |
| Release approval | Owner | YES |

## Escalation Rules

1. Any agent may escalate a concern to the Factory Lead Agent.
2. If the Factory Lead Agent cannot resolve, escalate to the Human Project Owner.
3. Security concerns rated HIGH or CRITICAL escalate immediately to the Owner.
4. Adversarial review findings that challenge factory core assumptions escalate to the Owner.
5. Capability adoption that would change the factory core or security posture requires Owner approval.

## Delegation Limits

- Agents may not delegate decisions outside their domain.
- Agents may not delegate safety, security, or governance decisions.
- The Owner may delegate specific decisions to specific teams but retains the right to review.
