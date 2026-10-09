# Independent Verification Team

> **Status:** PROPOSED

## Purpose

Test and verify implementations independently. Produce evidence that
claims about correctness, security, and quality are substantiated.

## Responsibilities

1. **Test Design**
   - Design tests based on acceptance criteria and traceability links.
   - Design tests that challenge assumptions.
   - Design negative and edge-case tests.

2. **Test Execution**
   - Execute tests and record results.
   - Produce test evidence (logs, coverage reports).
   - Report failures with reproduction steps.

3. **Evidence Verification**
   - Verify that evidence claims are truthful and complete.
   - Check evidence provenance (who produced it, when).
   - Flag stale or unverifiable evidence.

4. **Regression Testing**
   - Maintain and run regression suites.
   - Report regressions from changes.

## Inputs

- Implementation artifacts (code, configuration).
- Acceptance criteria linked to requirements.
- Evidence from Delivery Engineering Team.

## Outputs

- Test plans and test cases.
- Test execution results and evidence.
- Evidence verification report.
- Regression test reports.

## Required Evidence

- Each test must link to a traceability node.
- Test results must include pass/fail status and metrics.
- Evidence must include provenance metadata.

## Authority Limits

- Can design and execute tests.
- Can reject evidence as insufficient or unverifiable.
- Can block implementation from proceeding if tests fail.
- Cannot modify implementation (that is the Delivery Engineering Team's role).

## Independence Requirements

- MUST be independent from the Delivery Engineering Team.
- Must NOT have written the code being tested.
- Must NOT have designed the architecture being verified.
