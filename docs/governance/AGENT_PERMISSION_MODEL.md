# Agent Permission Model

> **Status:** PROPOSED - Subject to owner approval

## Overview

This document defines what agents are permitted to do, within what scope, and
with what oversight. Permissions are expressed as capability sets with explicit
boundaries.

## Permission Tiers

| Tier | Description | Scope | Oversight |
|---|---|---|---|
| TIER-0 | Unrestricted (Owner) | All domains, all decisions | None required |
| TIER-1 | Full domain (Team Lead) | Own team domain + coordination | Adversarial review for cross-domain impact |
| TIER-2 | Standard domain (Team Agent) | Within team domain and authority limits | Team lead review |
| TIER-3 | Restricted domain (Research/Sandbox) | Research, experimentation, proposals only | Owner approval for promotion |
| TIER-4 | Read-only (Observational) | Read all artifacts, no writes | None |

## Domain Permissions

| Domain | TIER-1 Lead | TIER-2 Agents | TIER-3 Agents |
|---|---|---|---|
| Governance | Owner only | None | None |
| Architecture | Architecture Traceability Team | All architecture authors | None |
| Implementation | Delivery Engineering Team | All implementation agents | Sandbox agents |
| Requirements | Requirements Discovery Team | All requirements analysts | None |
| Traceability | Architecture Traceability Team | All trace authors | None |
| Research | Capability Research Lab | All research agents | All research agents |
| Security | Security Threat Intelligence Team | Delivery Engineering Team (remediation) | Research agents (advisory only) |
| Validation | Independent Verification Team | Delivery Engineering Team | None |

## Cross-Team Permissions

- Agents may read artifacts from any team within their TIER-1 domain.
- Agents may write only to artifacts within their assigned team.
- Cross-team writes require TIER-1 approval from the target team lead.
- Adversarial reviewers may flag issues across all domains.

## Prohibited Actions (All Non-Owner Agents)

1. Modifying governance documents.
2. Adding or modifying secrets, credentials, or personal data.
3. Performing destructive git operations (force-push, reset --hard, etc.).
4. Promoting capabilities to APPROVED or ACTIVE without owner approval.
5. Modifying autonomy boundaries or safety constraints.
6. Silently changing factory core configuration.
7. Merging experimental capabilities into trusted production configuration.

## Capability Governance for New Project

> **Status:** PROPOSED - Not yet approved

The existing 20-skill restriction from the AI-DSS setup is proposed to NOT
apply to this project. Instead, the following capability governance model is
proposed:

1. No hard cap on the number of skills.
2. Each skill must pass through the capability adoption lifecycle.
3. Skills used in trusted production configuration must reach APPROVED status.
4. Skills in EXPERIMENTAL stage may be used only in sandboxed contexts.
5. The Owner may set a cap at any tier if desired (PENDING decision).
