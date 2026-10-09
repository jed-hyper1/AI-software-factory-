# Agent Framework Evaluation

> **Status:** PROPOSED

## Purpose

Evaluate agent frameworks (LangGraph, OpenAI Agents SDK, CrewAI, D SH,
etc.) for suitability as factory execution environments.

## Evaluation Criteria

| Criterion | Description | Scoring |
|---|---|---|
| Multi-agent support | Native support for multiple coordinated agents | 1-5 |
| Memory/state management | Built-in state and context persistence | 1-5 |
| Tool integration | Ease of adding custom tools and adapters | 1-5 |
| Orchestration patterns | Support for sequential, parallel, iterative workflows | 1-5 |
| Observability | Tracing, logging, and monitoring support | 1-5 |
| Failure recovery | Checkpointing, retry, and state restoration | 1-5 |
| Security | Built-in auth, permissioning, sandboxing | 1-5 |
| Community/maintenance | Active development, community support | 1-5 |
| Documentation | Quality and completeness of docs | 1-5 |
| Cost | Licensing, hosting, and operational costs | 1-5 |

## Evaluation Process

1. Create a standard test scenario (e.g., requirements discovery workflow).
2. Implement the scenario in each candidate framework.
3. Score each criterion with evidence.
4. Compare scores and identify trade-offs.
5. Recommend primary and fallback frameworks.

## Frameworks Under Consideration

| Framework | Status | Last Evaluated | Score |
|---|---|---|---|
| LangGraph | DISCOVERED | UNKNOWN | UNKNOWN |
| OpenAI Agents SDK | DISCOVERED | UNKNOWN | UNKNOWN |
| CrewAI | DISCOVERED | UNKNOWN | UNKNOWN |
| DeepSeek Harness (DSH) | DISCOVERED | UNKNOWN | UNKNOWN |
| AutoGen | DISCOVERED | UNKNOWN | UNKNOWN |

## Framework Evaluation Report Template

```
### [Framework Name] Evaluation

- **Version:** [Version evaluated]
- **Source:** [URL]
- **Maturity:** [Evidence of maintenance and adoption]
- **Scores:** [Table of criterion scores with evidence]
- **Strengths:** [List]
- **Weaknesses:** [List]
- **Recommendation:** [Adopt / Monitor / Reject]
- **Migration Requirements:** [If replacing another framework]
```

## Existing Baseline

The existing agent framework configuration (Codex, DSH) is assessed as
a reference baseline during Phase 1. See [STATUS.md](../../STATUS.md) for the current assessment.
