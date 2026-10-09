# Model Evaluation Protocol

> **Status:** PROPOSED

## Purpose

Provide a standardized protocol for evaluating AI models used by the factory.

## Evaluation Dimensions

| Dimension | Description | Measurement |
|---|---|---|
| Correctness | Accuracy on task-specific benchmarks | Pass rate, F1, accuracy |
| Completeness | Coverage of edge cases and failure modes | Coverage metrics |
| Consistency | Stable behavior across runs and inputs | Variance, std dev |
| Latency | Response time for single requests | p50, p95, p99 |
| Throughput | Requests processed per unit time | RPS, tokens/sec |
| Cost | Monetary cost per operation | $/request, $/token |
| Safety | Alignment with intended behavior, refusal of harmful requests | Refusal rate, safety benchmarks |
| Hallucination | Tendency to produce false or ungrounded output | Hallucination rate |
| Context Window | Maximum input length | Tokens |
| Tool Use | Ability to use tools effectively | Tool call accuracy, success rate |

## Evaluation Process

### Step 1: Define Evaluation Criteria

1. Map factory use cases to evaluation dimensions.
2. Select representative benchmark datasets.
3. Define pass/fail thresholds for each dimension.

### Step 2: Execute Evaluation

1. Run model on all benchmarks in a controlled environment.
2. Collect metrics for each dimension.
3. Record environmental conditions (model version, SDK version, etc.).

### Step 3: Analyze Results

1. Compare against thresholds.
2. Compare against baseline and alternative models.
3. Identify strengths and weaknesses.

### Step 4: Document

1. Publish evaluation report with metrics.
2. Record recommendation (adopt, monitor, reject).
3. Update capability registry.

## Reproducibility

All evaluations must be reproducible:

- Benchmark datasets must be version-pinned.
- Evaluation scripts must be version-controlled.
- Environmental configuration must be recorded.
- Results must include checksums or identifiers for reproduction.

## Evaluation Report Template

```
### Model: [Name and Version]

- **Provider:** [URL]
- **Evaluated on:** [Date]
- **Environment:** [SDK versions, hardware]
- **Datasets:** [List with versions]
- **Results:** [Table of metrics]
- **Comparison:** [vs baseline/alternatives]
- **Recommendation:** [Adopt / Monitor / Reject]
- **Limitations:** [Known limitations]
- **Reproducibility:** [Checksum or reference]
```
