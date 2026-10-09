# Development Roadmap

> **Status:** Phase 0 COMPLETE; Phase 1 IN PROGRESS

## Phases

| Phase | Name | Duration (est.) | Entry Criteria | Exit Criteria |
|---|---|---|---|---|
| P0 | Foundation | 2-4 weeks | Repository created, vision approved | Core docs, governance, and architecture published; implementation plan approved |
| P1 | Reference Baseline | 1-2 weeks | P0 complete | Existing setup assessed with evidence; capability gaps catalogued |
| P2 | Pilot Implementation | 2-4 weeks | P1 complete | First project pack implemented end-to-end with traceability; gates tested |
| P3 | Scaling & Automation | 4-8 weeks | P2 complete | Multiple packs supported; automation operational; research process running |
| P4 | Self-Improvement | 4+ weeks | P3 complete | Factory demonstrates evidence-backed self-improvement |

## Phase 0: Foundation (COMPLETE)

- [x] Publish all 50 required documentation files.
- [x] Validate internal links and cross-references (0 broken links).
- [x] Create [docs/implementation/INITIAL_IMPLEMENTATION_PLAN.md](docs/implementation/INITIAL_IMPLEMENTATION_PLAN.md).
- [x] Commit, push, and verify remote (commits c42644f, 5bc8ba1).
- [x] STATUS.md and ROADMAP.md updated after publication.

**Evidence:** 50 files, ~3,470 lines, committed to https://github.com/jed-hyper1/AI-software-factory-.git (commit 5bc8ba1)

## Phase 1: Reference Baseline Assessment (IN PROGRESS)

- [x] Assess DeepSeek Harness (DSH): configuration and execution evidence.
- [x] DSH hygiene gate audit: rescope-vendor:check fixed (3 files added to GENERIC_SKIPS).
- [x] DSH working tree: .claude/skills symlink restored.
- [x] Hygiene check re-run: 17 passed, 1 failed (verify-cordis-config — PRE-EXISTING, not introduced by audit).
- [x] AGENTS.md requirements checklist: 68 requirements documented with PASS/PARTIAL/FAIL status.
- [ ] Assess Codex orchestration: execution evidence (CONFIGURED_UNVERIFIED — config reviewed, not yet executed).
- [ ] Assess Loop Engineering: execution evidence (CONFIGURED_UNVERIFIED — referenced in AGENTS.md, not yet tested).
- [ ] Assess DDD adversarial review: integration mapping (PENDING).
- [ ] Assess agent skills and tool integrations: CLI-Anything evaluated (not installed — owner approval needed).
- [ ] Identify gaps and recommend retain / repair / extend / replace / defer.
- [x] DEEPSEEK_HARNESS_SETUP_AUDIT.md produced and published.
- [x] CLI_ANYTHING_INTEGRATION_REPORT.md produced and published.
- [ ] Propose separate capability governance policy (does NOT inherit 20-skill restriction).

## Phase 2: Pilot Implementation (PENDING)

- Select a simple pilot project pack (PENDING owner approval).
- Implement end-to-end: discovery to release.
- Demonstrate bidirectional traceability.
- Validate all phase gates and verification gates.

## Phase 3: Scaling & Automation (PENDING)

- Support multiple domain project packs.
- Automate standard factory workflows.
- Operationalize continuous research process.

## Phase 4: Self-Improvement (PENDING)

- Factory demonstrates evidence-backed self-improvement.

## Pending Deliverables

| Deliverable | Phase | Status |
|---|---|---|
| DEEPSEEK_HARNESS_SETUP_AUDIT.md | P1 | COMPLETE (published) |
| CLI_ANYTHING_INTEGRATION_REPORT.md | C | COMPLETE (published) |
| BLACK_BOX_SIMULATION_PLAN.md | D | PENDING |
| REQUIREMENT_SCENARIO_TRACEABILITY.md | D | PENDING |
| EVIDENCE_AND_METRICS_PLAN.md | E | PENDING |
| BENCHMARK_RESULTS.md | E | PENDING |
| INTEGRATION_TEST_REPORT.md | G | PENDING |
| REMEDIATION_AND_READINESS_REPORT.md | H | PENDING |

## Exit Criteria

- All required documentation exists and is cross-linked.
- Decisions and implementation status are accurately labeled.
- Known gaps and unresolved decisions remain visible and labeled.
- Changes are committed and pushed to GitHub.
