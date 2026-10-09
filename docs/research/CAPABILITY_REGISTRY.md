# Capability Registry

> **Status:** PROPOSED

## Purpose

A centralized, machine-readable registry of all AI models, frameworks,
tools, skills, and engineering methods evaluated by the factory.

## Registry Entry Format

```
### [Capability Name] v[Version]

- **Type:** [Model / Framework / Tool / Skill / Method / Protocol]
- **Provider/Source:** [Organization or repository URL]
- **Discovered:** [Date]
- **Maturity Evidence:** [Links to maintenance status, community activity]
- **Factory Gap:** [How this addresses a factory gap]
- **Compatibility:** [Integration requirements, version constraints]
- **Security Implications:** [Permission model, data flow, attack surface]
- **Benchmark Plan:** [Link to benchmark definition]
- **Benchmark Results:** [Link to results or PENDING]
- **Cost/Latency:** [Operational burden assessment]
- **Recommendation:** [Adopt / Monitor / Reject] (PENDING)
- **Lifecycle Stage:** DISCOVERED / SCREENED / EXPERIMENTAL /
  BENCHMARKED / APPROVED / ACTIVE / DEPRECATED
- **Status:** [PENDING approval where applicable]
```

## Registry Organization

The registry is organized by capability type:

- **MODELS/** -- AI models (language, vision, multimodal).
- **FRAMEWORKS/** -- Agent frameworks and orchestration systems.
- **TOOLS/** -- Development tools, utilities, and integrations.
- **SKILLS/** -- Agent skills (from the skill catalog or custom).
- **METHODS/** -- Engineering practices and methodologies.
- **PROTOCOLS/** -- Communication and integration protocols.

## Registry Maintenance

1. Capability Research Lab maintains the registry.
2. Entries are updated as lifecycle stage changes.
3. Rejected candidates are retained with reasons.
4. The Owner reviews and approves APPROVED and ACTIVE entries.

## Sample Entries

### OpenAI GPT-4o

- **Type:** Model
- **Provider/Source:** OpenAI
- **Discovered:** 2024-05-13
- **Maturity Evidence:** Active development, wide adoption
- **Factory Gap:** Primary reasoning model for agent tasks
- **Lifecycle Stage:** APPROVED
- **Status:** PENDING owner confirmation

### DeepSeek Harness (DSH)

- **Type:** Framework
- **Provider/Source:** https://github.com/deepseek-ai
- **Discovered:** 2025-01-20
- **Maturity Evidence:** Existing configuration in AI-DSS baseline
- **Factory Gap:** Agent orchestration and harness
- **Lifecycle Stage:** EXPERIMENTAL
- **Status:** PENDING evaluation during Phase 1
