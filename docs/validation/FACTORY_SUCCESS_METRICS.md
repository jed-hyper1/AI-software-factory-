# Factory Success Metrics

> **Status:** PROPOSED

## Purpose

Define measurable metrics for factory effectiveness, quality, and safety.

## Metric Categories

### 1. Quality Metrics

| Metric | Definition | Target | Status |
|---|---|---|---|
| Requirements discovery rate | % of missing/ambiguous requirements found before implementation | >90% | PLANNED |
| Traceability completeness | % of artifacts linked bidirectionally | 100% | PLANNED |
| Adversarial findings rate | Average findings per artifact review | <3 (HIGH+) | PLANNED |
| Evidence rejection rate | % of evidence rejected by verification | <10% | PLANNED |

### 2. Efficiency Metrics

| Metric | Definition | Target | Status |
|---|---|---|---|
| Agent coordination latency | Time between team handoffs | <60 min | PLANNED |
| Phase gate cycle time | Time to complete a phase | <7 days | PLANNED |
| Capability evaluation throughput | Evaluations per week | >2 | PLANNED |

### 3. Safety Metrics

| Metric | Definition | Target | Status |
|---|---|---|---|
| Unauthorized scope changes | Count of unapproved authority expansions | 0 | PLANNED |
| Security findings | CRITICAL/HIGH vulnerabilities found | 0 | PLANNED |
| Evidence tampering | Detected tampering incidents | 0 | PLANNED |
| Residual risk | Unmitigated risk score | <10 | PLANNED |

### 4. Research Metrics

| Metric | Definition | Target | Status |
|---|---|---|---|
| Landscape coverage | % of monitored categories updated weekly | >90% | PLANNED |
| Capability adoption rate | New capabilities through lifecycle per month | >1 | PLANNED |
| Benchmark reproducibility | % of benchmarks re-run with identical results | >95% | PLANNED |

## Metric Collection

Metrics are collected from:

- Traceability Store (completeness, coverage).
- Evidence Store (rejection rates, freshness).
- Orchestration Engine (cycle times, handoff latency).
- Security Service (findings, residual risk).
- Research Service (capability throughput, benchmark results).

## Reporting

- Daily: Automated collection and basic reporting.
- Weekly: Team-level metric review.
- Monthly: Factory-wide metric review and Owner presentation.
- Quarterly: Metric target review and adjustment.
