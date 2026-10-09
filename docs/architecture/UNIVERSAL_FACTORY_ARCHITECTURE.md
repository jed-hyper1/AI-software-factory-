# Universal Factory Architecture

> **Status:** PROPOSED

## Layered Architecture

The factory is organized into layers, each with a distinct concern. Layers
depend only on layers below them (no upward or lateral dependencies without
explicit mediation through the Orchestration Layer).

```
+-------------------------------------------------------------+
|  L5: Project Pack (Project-specific requirements, rules,   |
|      technology choices, acceptance criteria)               |
+-------------------------------------------------------------+
|  L4: Application / Orchestration (Agent teams, workflows)   |
+-------------------------------------------------------------+
|  L3: Factory Core Services (Memory, evidence, traceability)|
+-------------------------------------------------------------+
|  L2: Agent Harness (Model adapters, tool integrations)      |
+-------------------------------------------------------------+
|  L1: Infrastructure (Storage, compute, network)             |
+-------------------------------------------------------------+
|  L0: Human Control (Owner authority, approval boundaries)   |
+-------------------------------------------------------------+
```

## Layer Descriptions

### L0: Human Control Layer

The ultimate authority layer. Contains the Human Project Owner, approval
policy, and phase gates. All other layers operate within boundaries defined
here.

### L1: Infrastructure Layer

Provides storage (version control, evidence store, memory store), compute
resources, and basic networking. May include cloud or local resources.

### L2: Agent Harness Layer

Abstracts model providers (OpenAI, Anthropic, DeepSeek, etc.) and tool
integrations. Provides a uniform interface to agents regardless of underlying
provider. See INTEGRATION_ADAPTERS.md.

### L3: Factory Core Services

Reusable services shared across all projects:

- Orchestration Engine: Manages agent team assignment, task routing,
  and workflow state machines.
- Evidence Store: Persistent, immutable record of all evidence.
- Traceability Store: Bidirectional traceability graph.
- Memory Service: Persistent state and context management.
- Security Service: Threat models, advisory feeds, policy enforcement.
- Research Service: Capability monitoring, benchmarking, evaluation.

### L4: Application / Orchestration Layer

Contains the agent team definitions and workflow orchestrations. Each team
is a specialization of the generic factory core. See docs/agents/.

### L5: Project Pack Layer

Project-specific requirements, domain rules, technology choices, and
acceptance criteria. A Project Pack parameterizes the factory core for a
specific software project. See FACTORY_CORE_AND_PROJECT_PACKS.md.

## Data Flow

1. Project Pack provides requirements and constraints.
2. Requirements Discovery Team discovers and resolves ambiguities.
3. Architecture Traceability Team produces design linked to requirements.
4. Delivery Engineering Team implements code linked to design.
5. Independent Verification Team tests and produces evidence.
6. Adversarial Review Team challenges all artifacts.
7. Security Threat Intelligence Team reviews for threats.
8. Capability Research Lab ensures best practices and current tools.
9. Factory Lead Agent coordinates, tracks, and reports to the Owner.

## Key Design Decisions

| Decision | Rationale | Status |
|---|---|---|
| Layered separation | Enables reuse across projects | APPROVED |
| Bidirectional traceability | Ensures no artifact is orphaned | APPROVED |
| Independent verification | Prevents self-verification bias | APPROVED |
| Adversarial review | Finds weaknesses primary agents miss | APPROVED |
| Adapter pattern for providers | Avoids vendor lock-in | APPROVED |
| Evidence store with immutability | Prevents tampering | APPROVED |
