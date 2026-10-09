# Vision: Universal AI Software Factory

> **Status:** PROPOSED - Subject to owner approval

## Long-Term Vision

The Universal AI Software Factory aims to be a general-purpose, self-improving
system for engineering software with AI agents. Rather than building software
one task at a time, the factory discovers, specifies, traces, builds, tests,
reviews, and releases software with verifiable evidence and human oversight
at the boundaries that matter.

The factory is universal in two senses:

1. Domain-agnostic: parameterized by a Project Pack to produce software in
   any domain (web, mobile, embedded, data pipelines, infrastructure, etc.).
2. Agent-agnostic: coordinates whichever specialist AI agents are available
   and appropriate, without locking into a single vendor or framework.

## Governing Principles

1. **Evidence over assertion.** Claims must be backed by verifiable evidence.
2. **Bidirectional traceability.** Every artifact traceable to and from every
   other artifact it relates to.
3. **Independent verification.** Primary agents never verify their own output.
4. **Requirement discovery first.** The factory assumes requirements are
   incomplete, ambiguous, or contradictory at the start.
5. **Human authority at the boundary.** The Human Project Owner is the final
   authority over governance and consequential decisions.
6. **No silent authority expansion.** The factory may not silently change its
   own governance or promote unapproved capabilities.
7. **Continuous capability evaluation.** Models, frameworks, tools, and skills
   are continuously researched, benchmarked, and evaluated.
8. **Security as first-class concern.** Security considered at every phase.
9. **Evidence-backed improvement.** Factory improves through controlled experiments.
10. **Transparency and auditability.** All decisions, evidence, and state changes
    are recorded in durable, queryable form.

## Scope (In vs Out)

**In scope:** Requirements discovery, architecture traceability, multi-agent
coordination, adversarial review, continuous research, security, validation,
evidence management, and bidirectional traceability.

**Out of scope (initially):** Building the factory runtime as a commercial
product; replacing existing configurations without authorization; guaranteeing
security or completeness; automating final release approval.

## Relationship to Existing Projects

The existing AI-DSS repository and its agent configuration serve as a
reference baseline. Components such as Codex orchestration, DeepSeek Harness
(DSH), Loop Engineering, DDD adversarial review, and agent skills are assessed
but not automatically adopted or discarded. See STATUS.md for details.
