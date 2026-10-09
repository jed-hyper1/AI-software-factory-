# Capability Research Lab

> **Status:** PROPOSED

## Purpose

Research and evaluate AI models, agent frameworks, tools, skills, protocols,
and engineering methods. Maintain the capability registry and adoption
lifecycle.

## Responsibilities

1. **Capability Discovery**
   - Monitor for new models, frameworks, tools, and methods.
   - Catalog discovered capabilities in the Capability Registry.

2. **Screening**
   - Apply initial screening criteria (license, maturity, security posture).
   - Assign DISCOVERED or SCREENED status.

3. **Benchmarking**
   - Design and execute benchmark tests for capabilities.
   - Record results with reproducible test definitions.

4. **Evaluation**
   - Evaluate capabilities against factory needs.
   - Produce evaluation reports with recommendations.

5. **Lifecycle Management**
   - Track capabilities through the adoption lifecycle.
   - Recommend promotion or deprecation.
   - Ensure no capability is promoted to APPROVED without Owner approval.

## Inputs

- Capability registry.
- Factory gap analysis.
- Research findings from AI Landscape team.
- Advisory feeds (security, model, tool).

## Outputs

- Capability evaluation reports.
- Benchmark results.
- Adoption recommendations.
- Lifecycle status updates.

## Required Evidence

- Each capability must have a reproducible benchmark/test definition.
- Evaluation reports must include cost, latency, and operational burden.
- Source provenance must be recorded.

## Authority Limits

- Can move capabilities from DISCOVERED to SCREENED.
- Can move capabilities from SCREENED to EXPERIMENTAL.
- Can move capabilities from BENCHMARKED (with evidence).
- Cannot promote to APPROVED without Owner approval.
- Cannot modify trusted production configuration without Owner approval.

## Independence Requirements

- Benchmarking should be done independently from capability adoption decisions.
- Evaluation should consider alternatives without bias toward currently
  active capabilities.

## Recruitment Criteria

- Familiarity with benchmark design and test reproducibility.
- Knowledge of multiple agent frameworks and model providers.
- Understanding of security evaluation methods.
