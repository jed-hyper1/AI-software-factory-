# Factory Core and Project Packs

> **Status:** PROPOSED

## Factory Core

The Factory Core is the reusable infrastructure and services shared across
all projects. It is stable, version-controlled, and changes to it require
Owner approval.

### Core Components

| Component | Responsibility | Ownership |
|---|---|---|
| Orchestration Engine | Agent team assignment, workflow state | Factory Lead Agent |
| Evidence Store | Immutable evidence records | Independent Verification Team |
| Traceability Store | Bidirectional traceability graph | Architecture Traceability Team |
| Memory Service | Persistent state and context | Factory Core Team |
| Security Service | Threat models, advisory feeds | Security Threat Intelligence Team |
| Research Service | Capability monitoring, benchmarking | Capability Research Lab |
| Phase Gate Engine | Phase transition validation | Governance Team |

### Core Interfaces

The Factory Core exposes interfaces (not implementations) that Project Packs
and agent teams use. This allows the core to evolve without breaking projects.

## Project Packs

A Project Pack is a directory (or module) containing project-specific:

1. Requirements -- in docs/requirements/ (project-specific subset).
2. Domain Rules -- constraints, regulations, or domain-specific logic.
3. Technology Choices -- frameworks, languages, deployment targets.
4. Acceptance Criteria -- project-specific definitions of done.
5. Integration Adapters -- project-specific tool connections.

### Project Pack Structure

```
project-packs/
  my-web-app/
    pack.yaml              (metadata, technology choices)
    requirements/          (project-specific requirements)
    domain-rules/          (domain constraints)
    acceptance-criteria/   (project-specific DoD)
    adapters/              (project-specific integrations)
```

### Project Pack Lifecycle

1. DISCOVERED: Project pack identified as a candidate.
2. APPROVED: Owner approves the pack for development.
3. ACTIVE: Factory builds the project using this pack.
4. ARCHIVED: Project complete, pack archived for reference.
5. DEPRECATED: Pack no longer recommended.

## Separation Rules

- Factory Core changes require Owner approval (Phase Gate).
- Project Pack changes require team review.
- Project Packs may not modify Factory Core internals.
- Factory Core may not impose Project Pack-specific logic.
