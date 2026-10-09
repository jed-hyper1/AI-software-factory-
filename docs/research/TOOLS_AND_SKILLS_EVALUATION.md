# Tools and Skills Evaluation

> **Status:** PROPOSED

## Purpose

Evaluate tools and agent skills for factory use. Each tool or skill must
pass through evaluation before being used in trusted production configuration.

## Evaluation Dimensions

| Dimension | Description | Scoring |
|---|---|---|
| Correctness | Produces correct results for expected inputs | 1-5 |
| Reliability | Consistently works without unexpected failures | 1-5 |
| Security | No known vulnerabilities, proper sandboxing | 1-5 |
| Performance | Acceptable latency and resource usage | 1-5 |
| Cost | Token/compute cost is reasonable | 1-5 |
| Maintainability | Actively maintained, clear documentation | 1-5 |
| Integration | Easy to integrate with the factory | 1-5 |
| Risk | Potential for harm if it malfunctions | 1-5 |

## Evaluation Process

### Step 1: Initial Screening

- License compatibility.
- Known security vulnerabilities.
- Maintenance status.
- Basic functionality test.

### Step 2: Detailed Evaluation

- Run standardized test suite.
- Score against evaluation dimensions.
- Document limitations and failure modes.

### Step 3: Security Review

- Review by Security Threat Intelligence Team.
- Check for data exfiltration, excessive permissions.
- Verify source provenance.

### Step 4: Recommendation

- Recommend: Adopt / Monitor / Reject.
- If Adopt: propose promotion to capability registry.

## Tool/Skill Evaluation Report Template

```
### Tool/Skill: [Name and Version]

- **Type:** [Tool / Skill / Library / Service]
- **Source:** [URL or repository]
- **Published:** [Date]
- **Intended Capability:** [Description]
- **Scores:** [Table of dimension scores with evidence]
- **Limitations:** [Known limitations]
- **Security Assessment:** [Summary]
- **Cost Impact:** [Token, compute, licensing costs]
- **Recommendation:** [Adopt / Monitor / Reject]
- **Migration Requirements:** [If replacing another tool]
```

## Existing Baseline

Agent skills from the existing setup are assessed as a reference baseline.
The 20-skill restriction from the existing setup is NOT automatically
inherited. See [docs/governance/APPROVAL_POLICY.md](../governance/APPROVAL_POLICY.md) and [docs/governance/AGENT_PERMISSION_MODEL.md](../governance/AGENT_PERMISSION_MODEL.md) for the
proposed capability governance model.
