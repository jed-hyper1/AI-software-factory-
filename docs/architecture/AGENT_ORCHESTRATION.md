# Agent Orchestration

> **Status:** PROPOSED

## Overview

Agent orchestration manages the assignment, sequencing, and coordination of
specialist AI agents. It ensures work flows through the correct teams in the
correct order, with proper evidence collection and review.

## Orchestration Patterns

### 1. Sequential Handoff

Team A completes work, passes evidence to Team B for review.
Used for: Requirements then Architecture then Implementation then Testing.

### 2. Parallel Investigation

Multiple teams investigate the same problem independently.
Used for: Adversarial review, security review, capability research.

### 3. Iterative Refinement

Teams iterate with feedback loops until evidence is accepted.
Used for: Requirements discovery, design review, test refinement.

### 4. Loop Engineering

Bounded feedback loops with explicit stop conditions and approval gates.
Used for: Self-improvement experiments, capability evaluation.

## Assignment Strategy

Agents are assigned to teams based on:

1. Capability match -- the agent's skills match the team's needs.
2. Workload -- distribute work evenly across available agents.
3. Independence requirements -- ensure verifying agents are independent
   from producing agents.
4. Cost -- prefer lower-cost agents for routine tasks.

## Coordination Protocol

1. Factory Lead Agent receives task from Project Pack.
2. Lead Agent assigns to Requirements Discovery Team.
3. Discovery Team produces requirements with REQ IDs.
4. Architecture Traceability Team produces design linked to REQ IDs.
5. Delivery Engineering Team implements, linked to design.
6. Independent Verification Team tests, linked to implementation.
7. Adversarial Review Team challenges all artifacts.
8. Security Threat Intelligence Team reviews for threats.
9. Capability Research Lab ensures method currency.
10. Lead Agent compiles evidence, presents to Owner at Phase Gate.

## State Management

The orchestration engine maintains:

- Current workflow state (which phase, what teams are active).
- Agent assignments and availability.
- Evidence collection status per requirement.
- Open issues and blockers.
- Traceability link completeness.

[STATE_MEMORY_AND_CONTEXT.md](STATE_MEMORY_AND_CONTEXT.md) for details.
