# Contributing to the Universal AI Software Factory

> **Status:** PROPOSED - Subject to owner approval

## How to Contribute

1. All contributions require review by the Human Project Owner or a delegated
   agent team.
2. Changes to governance, architecture, authority, or security scope
   REQUIRE explicit owner approval.
3. All changes must maintain or improve traceability links.
4. New decisions must be recorded in [docs/governance/DECISION_REGISTER.md](docs/governance/DECISION_REGISTER.md).
5. Capability additions must follow the [CAPABILITY adoption lifecycle](docs/research/CAPABILITY_ADOPTION_LIFECYCLE.md).

## Change Review Process

1. Propose changes as a branch from main.
2. Submit a pull request with: change summary, rationale, evidence,
   impact analysis, and traceability updates.
3. Required reviewers: at least one from each affected domain team.
4. Adversarial review required for any autonomy or authority changes.
5. Owner approval required for phase gate transitions and governance changes.
6. All links and references must be validated before merge.

## Commit Conventions

- Use conventional commit format: `type(scope): description`.
- Reference requirement IDs and traceability links in commit messages.
- Do NOT commit secrets, credentials, or personal data.

## Label Conventions

- Status labels on documents: PROPOSED, PENDING, APPROVED, VERIFIED, UNKNOWN,
  REQUIRES OWNER APPROVAL.
- Component status labels: VERIFIED_WORKING, PARTIALLY_VERIFIED,
  CONFIGURED_UNVERIFIED, FAILED, NOT_PRESENT, NOT_APPLICABLE.
