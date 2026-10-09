# Evidence and Claim Verification

> **Status:** PROPOSED

## Purpose

Define how evidence supports claims, how claims are verified, and how stale
or unverifiable evidence is handled.

## Evidence Types

| Type | Description | Verification Method |
|---|---|---|
| Test Result | Pass/fail outcome of a test | Re-execution or log inspection |
| Build Output | Compiled artifact or build success | Re-build or artifact inspection |
| Benchmark | Performance or capability measurement | Re-run benchmark with same config |
| Review | Peer/authority review sign-off | Re-review by different agent |
| Advisory | Security advisory or threat feed entry | Cross-reference source |
| Inspection | Manual inspection of artifact | Re-inspection by different agent |

## Evidence Record Format

```
### EVID-[TYPE]-[NUMBER]: [Short Title]

- **Claim:** [What this evidence supports]
- **Produced by:** [Agent/team name and instance ID]
- **Produced at:** [ISO 8601 timestamp]
- **Source:** [File, log, or artifact reference]
- **Method:** [How evidence was collected]
- **Checksum:** [SHA-256 of the evidence artifact]
- **Status:** Fresh / Stale / Disputed / Verified
- **Verifies:** [Link to claim or artifact]
```

## Claim Verification Protocol

1. **Claim Identification:** Identify the claim being made.
2. **Evidence Collection:** Gather supporting evidence from the Evidence Store.
3. **Evidence Inspection:** Inspect the evidence for completeness.
4. **Provenance Check:** Verify who produced the evidence and when.
5. **Reproducibility Check:** Determine if the evidence can be reproduced.
6. **Verification Decision:** Accept, reject, or request fresh evidence.

## Stale Evidence Handling

Evidence becomes stale when:

- The artifact it supports has changed.
- A newer version of the evidence is available.
- The evidence age exceeds a defined threshold.
- The producing agent is no longer available for verification.

Stale evidence is flagged and may not be used to support claims until refreshed.

## Disputed Evidence

When adversarial review disputes an evidence item:

1. The claim is suspended pending resolution.
2. A fresh investigation is conducted by an independent agent.
3. If evidence cannot be reproduced, it is rejected.
4. The resolution is recorded in the Evidence Store.

## Evidence Immutability

- Evidence Store is append-only.
- Existing evidence records cannot be modified.
- Corrections are recorded as new evidence items referencing the old.
- Tampering is detected via checksum verification.
