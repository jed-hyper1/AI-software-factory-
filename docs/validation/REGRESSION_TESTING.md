# Regression Testing

> **Status:** PROPOSED

## Purpose

Ensure changes to the factory do not break existing functionality.

## Regression Test Strategy

### 1. Test Inventory

Maintain a registry of regression tests covering:

- Requirements discovery and ambiguity detection.
- Traceability link creation and validation.
- Evidence submission and immutability.
- Phase gate enforcement.
- Capability adoption lifecycle transitions.
- Security gate compliance.

### 2. Automation

- Regression tests are automated and run on every factory core change.
- Results are recorded as evidence.
- Failures block promotion to APPROVED status.

### 3. Regression Test Format

```
### REG-[ID]: [Test Name]

- **Scope:** What is tested
- **Trigger:** When this test runs
- **Steps:** Test execution steps
- **Expected:** Pass/fail criteria
- **Evidence:** Where evidence is stored
- **Status:** PLANNED / PASS / FAIL
```

## Planned Regression Tests

| ID | Description | Status |
|---|---|---|
| REG-001 | Evidence immutability after factory core change | PLANNED |
| REG-002 | Traceability link integrity after refactor | PLANNED |
| REG-003 | Phase gate enforcement after config change | PLANNED |
| REG-004 | Capability lifecycle state persistence | PLANNED |
