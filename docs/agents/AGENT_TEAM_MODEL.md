# Agent Team Model

> **Status:** PROPOSED

## Overview

An Agent Team is a logical role within the factory, not necessarily a single
permanently-running agent. Teams define inputs, outputs, required evidence,
authority limits, independence requirements, escalation rules, and recruitment
criteria.

Agents are assigned to teams based on capability, workload, cost, and
independence requirements. A single agent may serve on multiple teams at
different times, but must never serve as both producer and verifier for the
same artifact.

## Team Independence Rule

The agent that produces an artifact must NOT be the sole agent that verifies it.
This rule applies at the team level: production teams are separate from
verification teams.

## Team Catalog

| Team | Focus | Primary Document |
|---|---|---|
| Requirements Discovery Team | Discover, clarify, resolve requirements | REQUIREMENTS_DISCOVERY_TEAM.md |
| Adversarial Review Team | Challenge and find weaknesses in deliverables | ADVERSARIAL_REVIEW_TEAM.md |
| Architecture Traceability Team | Design and maintain traceability | ARCHITECTURE_TRACEABILITY_TEAM.md |
| Delivery Engineering Team | Implement code and configuration | DELIVERY_ENGINEERING_TEAM.md |
| Independent Verification Team | Test and verify implementations | INDEPENDENT_VERIFICATION_TEAM.md |
| Security Threat Intelligence Team | Threat modeling and monitoring | SECURITY_THREAT_INTELLIGENCE_TEAM.md |
| Capability Research Lab | Evaluate models, tools, skills | CAPABILITY_RESEARCH_LAB.md |
| AI Landscape and Factory Evolution | Track practices and self-improve | AI_LANDSCAPE_AND_FACTORY_EVOLUTION.md |

## Team Lifecycle

### 1. Activation

- Task is assigned by the Factory Lead Agent.
- Required capabilities are checked against the capability registry.
- Agent(s) are assigned based on capability, workload, and independence.

### 2. Execution

- Team works within its defined scope and authority.
- All decisions and evidence are recorded in the Evidence Store.
- Status is tracked in the orchestration engine.

### 3. Handoff

- Team delivers its output and evidence.
- Output is linked to relevant requirements and design.
- Next team is notified and begins their review.

### 4. Review

- Adversarial Review Team validates the output.
- If issues found, work returns to the producing team for remediation.
- If accepted, work proceeds to the next phase.

### 5. Closure

- Team's work is complete and evidence is archived.
- Lessons learned are recorded for future reference.

## Team Composition

Teams need not map to permanently running agents. Agent assignment is based on:

- **Capability** -- Does the agent have the required skills?
- **Workload** -- Is the agent available?
- **Cost** -- Can a lower-cost agent handle this?
- **Independence** -- Is the agent independent from related teams?

## Recruitment Criteria

New agents are recruited based on:

1. Demonstrated capability in the team's domain.
2. Passing of team-specific evaluation criteria.
3. Adherence to the Authority Model and Permission Model.
4. Ability to produce and consume evidence.
