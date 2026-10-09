# Approval Policy

> **Status:** PROPOSED - Subject to owner approval

## Overview

This document defines what decisions agents may make autonomously, what requires
explicit approval, and what must be escalated to the Human Project Owner.

## Approval Categories

### Category A: Fully Autonomous (No Approval Needed)

- Writing, updating, and publishing documentation.
- Creating internal notes, evidence records, and traceability links.
- Running validation checks and recording results.
- Proposing research topics and initial capability candidates.
- Internal code formatting, linting, and refactoring (non-behavioral).
- Creating branches (non-destructive git operations).

### Category B: Requires Agent Review (Not Owner)

- Adding a new capability to the EXPERIMENTAL or BENCHMARKED stage of the
  lifecycle.
- Modifying non-governance documentation (architecture, agent teams, etc.).
- Proposing changes to existing traceability links.
- Submitting pull requests for non-governance changes.

### Category C: Requires Owner Approval

- Changing the license or adding a LICENSE file.
- Modifying governance documents (this category, authority model, etc.).
- Changing the authority model or agent permission model.
- Modifying autonomy boundaries or safety/security constraints.
- Promoting a capability to APPROVED or ACTIVE stage.
- Transitioning between major development phases (phase gates).
- Final release approval or production deployment.
- Accepting residual security risk above LOW.
- Changing dependency or supply-chain policies.

### Category D: Must be Escalated (Blocked Without Approval)

- Force-push, history rewrite, or destructive git operations.
- Adding secrets, credentials, or personal data to any file.
- Merging experimental/unverified capabilities into trusted configuration.
- Silently changing factory governance.
- Expanding authority scope without explicit approval.

## Approval Process

1. **Proposal:** The proposing agent submits a proposal with rationale, evidence,
   and impact analysis.
2. **Review:** The proposal is reviewed by the appropriate authority (agent team
   lead, adversarial reviewer, or owner).
3. **Decision:** The reviewer either approves or rejects with explanation.
4. **Record:** The decision is recorded in the DECISION_REGISTER.md.

## Default Approval Setting

Unless explicitly overridden by the Human Project Owner, the default approval
policy for this project is **"ask"** -- meaning any action that would modify
governance, expand authority, or accept significant risk requires explicit owner
confirmation.

## Current Approval Policy State

- **Policy:** ask
  - Changed by the user from "ask" to "never".
  - When "never," actions requiring approval are rejected automatically.
  - This is reflected in the current session configuration.

## Change of Approval Policy

The Human Project Owner may change the approval policy at any time. Proposed
changes must be recorded in the DECISION_REGISTER.md and documented in this file.
