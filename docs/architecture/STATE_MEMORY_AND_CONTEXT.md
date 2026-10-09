# State, Memory, and Context

> **Status:** PROPOSED

## Overview

The factory must manage state, memory, and context across agent sessions,
teams, and projects. This document defines the memory architecture.

## Memory Layers

| Layer | Duration | Scope | Storage |
|---|---|---|---|
| Working Memory | Single task | Agent instance | In-context |
| Session Memory | Single project run | Project Pack | Local file / DB |
| Factory Memory | Across projects | All projects | Persistent store |
| Domain Memory | Long-term | Knowledge base | Vector store |

### Working Memory

The agent's context window. Limited by token budget. Contains the current
task, relevant requirements, recent evidence, and instructions.

## Context Management

### Context Budgeting

Each agent task has a context budget. The orchestration engine tracks
token usage and trims or summarizes context when approaching the limit.

### Context Compression

When context exceeds budget:

1. Summarize older conversation turns.
2. Prune redundant information.
3. Offload evidence to the Evidence Store.
4. Retrieve relevant artifacts from the Traceability Store as needed.

### Session Memory

Per-project state: requirements discovered, architecture decisions,
implementation progress, test results, and evidence collected.

### Factory Memory

Cross-project knowledge: capability evaluations, lessons learned,
process improvements, and reusable patterns.

### Domain Memory

Long-term knowledge: security advisories, model benchmarks, threat
intelligence, and research findings. Indexed for retrieval.

## Loop Engineering Integration

Bounded feedback loops with explicit stop conditions are used for:

- Requirements refinement (stop when ambiguity below threshold).
- Test improvement (stop when coverage meets target).
- Capability evaluation (stop when benchmark threshold met).

[docs/agents/AI_LANDSCAPE_AND_FACTORY_EVOLUTION.md](../agents/AI_LANDSCAPE_AND_FACTORY_EVOLUTION.md).
