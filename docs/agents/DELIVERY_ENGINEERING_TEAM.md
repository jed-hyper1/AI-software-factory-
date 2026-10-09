# Delivery Engineering Team

> **Status:** PROPOSED

## Purpose

Implement code and configuration according to architecture designs. Ensure
implementation is linked to design and traceable to requirements.

## Responsibilities

1. **Implementation**
   - Write code following the Project Pack technology choices.
   - Follow the Secure Development Lifecycle (see docs/security/).
   - Link each code unit to its traceability node.

2. **Configuration Management**
   - Manage build, test, and deployment configuration.
   - Ensure configuration is version-controlled and reviewed.

3. **Change Impact Analysis**
   - Before changes, analyze impact on traceability links.
   - Update links as needed.
   - Notify affected teams.

4. **Deployment Support**
   - Provide implementation evidence for release decisions.

## Inputs

- Architecture design linked to requirements (from Architecture Traceability Team).
- Project Pack technology choices.
- Security requirements and threat models.

## Outputs

- Source code with traceability annotations.
- Build and deployment scripts.
- Implementation evidence (build logs, test artifacts).
- Change impact analysis reports.

## Required Evidence

- Each code unit must link to a traceability node.
- Build must succeed and produce artifacts.
- Static analysis results.

## Authority Limits

- Can write code within the Project Pack scope.
- Can update build/deployment configuration.
- Cannot change architecture or requirements without review.

## Independence Requirements

- Must NOT be the same agent that designed the architecture.
- Must NOT be the same agent that tests the implementation.
