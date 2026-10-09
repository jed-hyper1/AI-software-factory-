# Evidence and Metrics Plan

**Date:** 2026-10-09
**Status:** PROPOSED

## 1. Research Questions

| ID | Question | Measurement Approach |
||--|--|
| RQ-01 | Does the framework identify more genuine missing requirements than baseline? | Manual vs framework requirement discovery on same input |
| RQ-02 | Does the framework reduce false-positive findings? | Precision of reported gaps vs manual review |
| RQ-03 | Can the framework produce reproducible results from identical inputs? | Repeat-run agreement |
| RQ-04 | Does tool integration improve task completion? | Task success rate with/without CLI-Anything |
| RQ-05 | Does evidence-backed review reduce unsupported conclusions? | Unsupported-claim rate |

## 2. Metrics

### Requirement Discovery
- Confirmed gap recall (vs independently established reference set)
- Precision of reported gaps
- False-positive rate
- Duplicate finding rate

### Task Execution
- Task success rate (completed / attempted)
- Expected-output conformance
- Integration success rate
- Human intervention frequency

### Evidence Quality
- Claim-to-source traceability (claims with citations / total claims)
- Source relevance and authority score
- Evidence completeness (evidence items / required evidence items)
- Unsupported-claim rate

### Efficiency
- Execution time per task
- Tool-call count per task
- Token usage where measurable

### Robustness
- Repeat-run agreement (identical results / total runs)
- Recovery after interruption
- Performance under degraded dependencies

## 3. Baseline and Comparisons

Baseline: Manual requirement review by human analyst on the same specification.
Comparison: Framework-assisted review (DSH agents + CLI-Anything tools).

Task sets: 5 specification documents of varying complexity.
Environment: Same DSH profile, same API key, same model.

## 4. Weights and Thresholds

No composite scores will be used. Individual metrics will be reported separately.
Numeric thresholds will only be used where explicitly justified per metric.

## 5. Independent Verification

All framework-generated claims will be cross-checked against source documents.
Two review passes: automated validation against reference sets, then human
judgment by the project owner as final decision-maker.

## 6. Artifact Preservation

Each evaluation run will produce:
- Run manifest (timestamp, commit, config version)
- Raw outputs (session logs, tool outputs)
- Metric calculations (CSV)
- Source references (URLs, dates accessed)
- Reviewer verdicts (PASS/FAIL/NOT_APPLICABLE)
- Known limitations and unresolved issues