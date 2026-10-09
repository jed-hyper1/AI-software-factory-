# Security Verification Gates

> **Status:** PROPOSED

## Purpose

Define explicit security checkpoints that must pass before proceeding to
the next phase or release.

## Verification Gates

| Gate | Trigger Point | Required Check | Pass Criteria | Responsible |
|---|---|---|---|---|
| G-SEC-01 | Before implementation | Threat model complete | All STRIDE categories assessed | Security Team |
| G-SEC-02 | Before code complete | Static analysis (SAST) | No CRITICAL or HIGH findings | Delivery + Security Teams |
| G-SEC-03 | Before testing | Dependency scan | No CRITICAL vulnerabilities | Security Team |
| G-SEC-04 | Before adversarial review | Secrets scan | No secrets detected | Security Team |
| G-SEC-05 | Before release | Final security review | No CRITICAL/HIGH outstanding | Security Team + Owner |

## Gate: G-SEC-01 (Threat Model)

Entry criteria:
- All requirements are assigned REQ IDs.
- Domain rules are documented.

Verification:
- Threat model produced using STRIDE.
- Attack surfaces identified.
- Mitigations assigned to each threat.

Pass criteria:
- All STRIDE categories assessed.
- All HIGH and CRITICAL threats have mitigations.
- MEDIUM threats have documented risk acceptance.

## Gate: G-SEC-02 (Static Analysis)

Entry criteria:
- Code implementation complete.

Verification:
- SAST scan passed.
- No hardcoded secrets.
- Input validation present.
- No known insecure patterns.

Pass criteria:
- No CRITICAL or HIGH findings.
- MEDIUM findings have remediation plans.

## Gate: G-SEC-03 (Dependency Scan)

Entry criteria:
- All dependencies declared.

Verification:
- Dependency scan completed.
- SBOM generated.
- No known CRITICAL vulnerabilities.

Pass criteria:
- All CRITICAL vulnerabilities remediated.
- HIGH vulnerabilities have risk acceptance.

## Gate: G-SEC-05 (Final Security Review)

Entry criteria:
- All prior gates passed.
- All tests completed.
- Adversarial review complete.
- No outstanding CRITICAL or HIGH findings.

Verification:
- Owner reviews residual risk.
- Final security sign-off.

Pass criteria:
- Owner accepts residual risk (if any remains).
- All security evidence is fresh and verified.
