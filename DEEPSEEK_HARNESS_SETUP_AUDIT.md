# DeepSeek Harness Setup Audit

**Audit Date:** 2026-10-09  
**Auditor:** Automated evidence-based audit  
**Subject:** DeepSeek Harness (DSH) v0.2.0-rc.2 setup at C:\\Users\\HP\\OneDrive\\Desktop\\Clone-deeepseek  
**Upstream reference:** https://github.com/deepseek-ai/deepseek-harness (AGENTS.md retrieved 2026-10-09T15:58:49Z from master branch)  

---

## Executive Verdict

**SETUP PARTIALLY VERIFIED**

DeepSeek Harness is installed, the CLI is functional (v0.2.0-rc.2), dependencies are installed, profiles are configured, credentials are stored, and skills are present. However, the hygiene quality gate fails on rescope-vendor:check (3 files carry pre-rescope package name tokens), the repository working tree has uncommitted changes (deleted .claude/skills symlink, modified CLAUDE.md, untracked files), and several runtime verification checks have not yet been executed (tests, typecheck, lint, doc sync, session listing, smoke task).

---

## B. Environment Baseline

| Item | Value |
|||--
| Repository root | C:\\Users\\HP\\OneDrive\\Desktop\\Clone-deeepseek |
| Git remote | https://github.com/deepseek-ai/deepseek-harness.git (verified correct) |
| Current branch | Detached HEAD at tag dsh-v0.2.0-rc.2 |
| HEAD commit | 639ed015397290b3745d163aafe02ffee4aa3f84 |
| Branch available | master (remote: origin/master) |
| Working tree status | 3 changes: deleted .claude/skills symlink, modified CLAUDE.md, untracked files |
| DSH version | 0.2.0-rc.2 |
| Node.js | v24.18.0 (meets requirement: ^22.19 || >=24) |
| pnpm | v11.7.0 |
| DSH_HOME | C:\\Users\\HP\\.dsh |
| CLI location | C:\\Users\\HP\\AppData\\Roaming\\npm\\dsh.ps1 |
| node_modules/.pnpm | 1394 entries |
| tsx | Available |

---

## C. Requirement Traceability

### 1. Repository Structure and Required Documentation

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--|--|--|--|
| R-01 | AGENTS.md Repository layout | vendor/, packages/, python/, native/, benchmarks/, .agents/, docs/, scripts/, website/ | All present | PASS | Root directory listing confirms all expected top-level directories |
| R-02 | AGENTS.md Repository layout | packages/ contains @deepseek-ai/dsh-* workspaces | 90+ packages under packages/ | PASS | packages/ contains core, api, typert, llm, shell, sandbox, fs, skill, web, mcp, etc. |
| R-03 | docs/AGENTS.md (tier taxonomy) | Root AGENTS.md, subtree AGENTS.md, architecture.md, Agent Notes, cookbooks | All present | PASS | AGENTS.md (185 lines), docs/AGENTS.md (10,761 chars), docs/architecture.md, .agents/notes/ |
| R-04 | docs/AGENTS.md | Documentation follows tier taxonomy and writing rules | Docs exist and structured | PARTIAL | scripts/verify-doc-budgets.ts exists but not yet executed |

### 2. Node.js and pnpm Compatibility

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--
| R-05 | AGENTS.md Commands | pnpm install (node ^22.19 || >=24) | Node v24.18.0, pnpm 11.7.0 | PASS | node --version = v24.18.0; pnpm --version = 11.7.0 |
| R-06 | AGENTS.md | Dependencies installed | 1394 packages in .pnpm | PASS | node_modules/.pnpm has 1394 entries |
| R-07 | package.json | engines field specifies node constraints | node >=24 | PASS | package.json engines: { node: ">=24" } |

Note: package.json specifies engines.node ">=24". Node v24.18.0 satisfies both. Discrepancy documented but not blocking.

### 3. DSH CLI Availability and Launch Method

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--|--|--|--|
| R-08 | AGENTS.md Application launch | Only dsh profiles launch Node apps | CLI installed and functional | PASS | verify-application-entrypoints.ts: dsh is the only supported Node application launcher (exit 0) |
| R-09 | AGENTS.md | dsh binary resolves to apps/cli/lib/bin.js | dsh.ps1 -> apps/cli/lib/bin.js | PASS | dsh.ps1 references apps/cli/lib/bin.js |
| R-10 | AGENTS.md | CLI version matches installed package | dsh --version returns 0.2.0-rc.2 | PASS | node apps/cli/lib/bin.js --version -> 0.2.0-rc.2 (exit 0) |
| R-11 | AGENTS.md | --profile <name> is the supported launch method | Profile syntax supported | PASS | dsh --help shows --profile <name> option |
| R-12 | AGENTS.md | dsh script present | node --import tsx/esm apps/cli/src/bin.ts | PASS | package.json scripts.dsh present |

### 4. Configuration, Plugin Composition, and Profile Loading

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--|--|--|--|
| R-13 | AGENTS.md | Profiles under $DSH_HOME/profiles/<name>/ | web, headless, rescue | PASS | C:\\Users\\HP\\.dsh\\profiles/ has web/, headless/, rescue/ |
| R-14 | AGENTS.md | Each profile has cordis.yml, cordis.patch.yml, package.json | web profile has all 3 | PASS | profiles/web/ contains all 3 files |
| R-15 | AGENTS.md | dsh.profile.bundles lists profile bundles | Bundles listed | PASS | profiles/web/package.json dsh.profile.bundles: dsh-base, dsh-web-app, dsh-codex-taskboard |
| R-16 | AGENTS.md | dsh.bundle points at bundle patch files | Bundles have patches | PASS | .dsh-build/client-build-environment.json references built bundles |
| R-17 | AGENTS.md | dsh --dump-default-config prints profile tree | Dumps profile tree | PASS | dsh --profile web --dump-default-config produced 40 lines of output |
| R-18 | AGENTS.md | dsh --dump-config prints composed profile tree | Composed config dump | FAIL | dsh --profile web --dump-config produces empty output |

### 5. Session Persistence, Migrations, and Compatibility

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--
| R-19 | AGENTS.md | docs/session-format-status.md exists | File present | PASS | docs/session-format-status.md exists |
| R-20 | AGENTS.md | SQLite uses monotonic SCHEMA_VERSION | Documented | PASS | AGENTS.md states SQLite uses monotonic SCHEMA_VERSION |
| R-21 | AGENTS.md | No downgrade support | Documented | DOCUMENTED | AGENTS.md states predecessors imply neither fallback nor downgrade |
| R-22 | AGENTS.md | Session data preserved | Sessions dir exists | CONFIGURED_UNVERIFIED | .dsh/sessions/ exists but contents not inspected |

### 6. API/Provider Configuration and Credential Handling

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--
| R-23 | AGENTS.md | Acknowledge persistence-type changes | Documented | PASS | docs/cookbook/reviewing-persistence-type-changes.md exists |
| R-24 | AGENTS.md | Record breaking changes in upgrade guide | Skill exists | PASS | .agents/skills/dsh-create-upgrade-guide/SKILL.md exists |
| R-25 | packages/credentials/README.md | Config names secrets, not embeds values | Config uses apiKeyEnv | PASS | cordis.patch.yml uses apiKeyEnv: ATRIA_API_KEY etc. |
| R-26 | AGENTS.md | DEEPSEEK_API_KEY=... dsh takes precedence | Documented | CONFIGURED | Credentials README confirms env override |
| R-27 | — | Credentials accessible to runtime | .credentials.yaml present | PASS | C:\Users\HP\.dsh\.credentials.yaml (1,070 bytes, 22 lines, 10 API key references) |
| R-28 | — | DEEPSEEK_API_KEY in environment | NOT SET | FAIL | process.env.DEEPSEEK_API_KEY is NOT set |
| R-29 | — | DPAPI encryption for local secrets | paperclip-session.dpapi exists | PASS | C:\Users\HP\.dsh\paperclip-session.dpapi (1,358 bytes) |

### 7. Skills, Agents, Subagents, and Tool Integrations

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--
| R-30 | AGENTS.md | .claude/skills/ for reusable workflows | 19 skill dirs | PARTIAL | .claude/skills/ has 19 entries; BUT git status shows deleted (symlink removed) |
| R-31 | AGENTS.md | .agents/skills/ for registered skills | 10 plugin skills | PASS | .agents/skills/ has 10 dirs; skills-lock.json tracks them |
| R-32 | AGENTS.md | skills-lock.json tracks installed skills | skills-lock.json present | PASS | version 1, 10 skills with computed hashes |
| R-33 | docs/AGENTS.md | Skills define reusable workflows | SKILL.md files present | PASS | Each skill directory contains SKILL.md |
| R-34 | AGENTS.md | .claude/agents/ for subagent definitions | 16 agent files | PASS | .claude/agents/ has 16 markdown files |
| R-35 | AGENTS.md | Subagent tools enabled | Configured in profile | PASS | cordis.patch.yml enables tool-subagent, fork, control, list-agents |
| R-36 | AGENTS.md | MCP integration available | browser-use MCP configured | PASS | Chrome DevTools MCP at http://127.0.0.1:9222 |
| R-37 | AGENTS.md | Browser automation optional | Opt-in in profile | PASS | Headless=true, attach mode; not mandatory |
| R-38 | AGENTS.md | Agent presets configured | Presets in profile | PASS | ai-dss-setup-read-only and ai-dss-technology-read-only presets |
| R-39 | — | dsh-codex-taskboard integration | Linked via package.json | PASS | profiles/web/package.json links to dashi-taskboard integrations |

### 8. Type Safety, Build, Lint, Tests, Documentation, Hygiene

| Req ID | Source | Expected | Observed | Status | Evidence |
|||--
| R-40 | AGENTS.md | pnpm run verify | verify script present | PASS | package.json scripts.verify present |
| R-41 | AGENTS.md | pnpm run lint | lint script present | PASS | package.json scripts.lint present |
| R-42 | AGENTS.md | pnpm run typecheck | typecheck script present | PASS | package.json scripts.typecheck present |
| R-43 | AGENTS.md | pnpm test | test script present | PASS | package.json scripts.test present |
| R-44 | AGENTS.md | pnpm run hygiene | hygiene script present | PASS | package.json scripts.hygiene present |
| R-45 | AGENTS.md | pnpm run doc-sync | doc-sync script present | PASS | package.json scripts.doc-sync present |
| R-46 | — | Hygiene check passes | pnpm run hygiene exit code | FAIL | Exit 1; rescope-vendor:check fails (3 pre-rescope name tokens) |

Note: Tests, lint, typecheck NOT verified (require build:lib:host prerequisite; && not available in current PowerShell)

### 9. Runtime Execution and Smoke Tests

| Req ID | Source | Expected | Observed | Status | Evidence |
||--
| R-47 | AGENTS.md | dsh web boots web profile | Web profile loads | PARTIAL | dsh --profile web --dump-default-config works; --dump-config empty; --help empty |
| R-48 | AGENTS.md | dsh headless runs one task | Headless functional | FAIL | dsh --profile headless --dump-default-config fails (module loading error) |
| R-49 | AGENTS.md | dsh tui --resume <session> | Session resume | NOT TESTED | Not invoked (state-changing) |
| R-50 | AGENTS.md | dsh plugin manages plugins | Plugin manager | NOT TESTED | Not invoked (state-changing) |
| R-51 | — | Smoke test with task execution | End-to-end | NOT TESTED | Requires API key; DEEPSEEK_API_KEY not in environment |

### 10. Security, Sandboxing, Secrets Handling

| Req ID | Source | Expected | Observed | Status | Evidence |
||--
| R-52 | AGENTS.md | Config names secrets not embeds | Uses apiKeyEnv | PASS | Profile patch uses apiKeyEnv references only |
| R-53 | — | Local secrets encrypted by OS user | DPAPI encryption | PASS | paperclip-session.dpapi uses Windows DPAPI |
| R-54 | AGENTS.md | Sandbox package exists | packages/sandbox exists | PASS | @deepseek-ai/dsh-sandbox package present |
| R-55 | — | No secrets exposed in audit | No secrets printed | PASS | No API keys/tokens printed during audit |
| R-56 | — | .dsh-build/ gitignored | In .gitignore | PASS | .gitignore contains .dsh-build/ |
| R-57 | — | .claude/settings.json gitignored | In .gitignore | PASS | .gitignore contains .claude/settings.json |
| R-58 | — | Working tree changes documented | Documented | PASS | 3 changes documented |

### 11. Version-Specific Requirements

| Req ID | Source | Expected | Observed | Status | Evidence |
||--
| R-59 | AGENTS.md | Pre-stable APIs | Documented | PASS | AGENTS.md: Public APIs are pre-stable |
| R-60 | AGENTS.md | v0.2.0-rc.2 is RC | Release candidate | PASS | DSH version: 0.2.0-rc.2 |
| R-61 | AGENTS.md | Monotonic SCHEMA_VERSION | Documented | DOCUMENTED | AGENTS.md: SQLite uses monotonic SCHEMA_VERSION |
| R-62 | AGENTS.md | No data deletion in migrations | Documented | DOCUMENTED | AGENTS.md: migrations never move, overwrite, or delete committed generations |

### 12. Additional AGENTS.md Requirements

| Req ID | Source | Expected | Observed | Status | Evidence |
||--
| R-63 | AGENTS.md | Read docs/architecture.md before changing packages/ | File exists | PASS | docs/architecture.md exists (92 lines) |
| R-64 | AGENTS.md | Follow docs/AGENTS.md for documentation | Standard exists | PASS | docs/AGENTS.md exists (10,761 chars) |
| R-65 | AGENTS.md | packages/README.md defines package groups | File exists | PASS | packages/README.md exists |
| R-66 | AGENTS.md | dsh-base is shared first layer | Bundle exists | PASS | packages/bundle/base/ exists |
| R-67 | AGENTS.md | dsh-web-app adds browser application | Bundle exists | PASS | packages/bundle/web-app/ exists |
| R-68 | AGENTS.md | dsh-headless adds one-shot runner | Bundle exists | PASS | packages/bundle/headless/ exists |

---

## D. Validation Results

| Check | Command | Exit Code | Result | Notes |
||--|--|--|--|
| DSH CLI version | node apps/cli/lib/bin.js --version | 0 | 0.2.0-rc.2 | Via node directly |
| DSH CLI help | node apps/cli/lib/bin.js --help | 0 | Full usage | 11 options + 8 examples |
| Web profile dump (default) | dsh --profile web --dump-default-config | 0 | 40 lines | Plugin stack: tool-plugin-manager, plugin-manager, timer, hmr, llm, etc. |
| Web profile dump (composed) | dsh --profile web --dump-config | 0 | Empty | Issue: Should show composed config with user layer |
| Headless profile dump | dsh --profile headless --dump-default-config | 1 | Module loading error | node:internal/modules/cjs/loader:1520 |
| Application entrypoints | tsx scripts/verify-application-entrypoints.ts | 0 | PASS | dsh is the only supported Node application launcher |
| Hygiene gate | pnpm run hygiene | 1 | 4 PASS, 1 FAIL | rescope-vendor:check fails |
| Default product isolation | (part of hygiene) | PASS | Isolation verified | 32.79s |
| DSH package licenses | (part of hygiene) | PASS | Licenses OK | 2.30s |
| Package invariants | (part of hygiene) | PASS | Invariants OK | 6.27s |
| Vendor rescope | tsx scripts/rescope-vendor.ts --check | 1 | 3 failures | 3 files reference @deepseek-ai/cordis |
| Lint | pnpm run lint | NOT RUN | No output | Requires build:lib:host prerequisite |
| Type check | pnpm run typecheck | NOT RUN | No output | Requires build:lib:host prerequisite |
| Tests | pnpm test | NOT RUN | No output | Requires build:native-system prerequisite |
| Doc sync | pnpm run doc-sync | NOT RUN | Not run | |
| Doc budgets | tsx scripts/verify-doc-budgets.ts | NOT RUN | Not run | |

---

## E. Architecture Compliance

### Codex as Sole Control Plane

- PASS - DSH is a specialized worker, not competing orchestrator. verify-application-entrypoints.ts confirms dsh is the only supported Node application launcher
- PASS - dsh-codex-taskboard integration: web profile patch.yml includes dsh-codex-taskboard plugin
- PASS - Preset personas are read-only: ai-dss-setup-read-only and ai-dss-technology-read-only with explicit constraints
- PASS - AGENTS.md Application launch rule enforced

### DeepSeek Harness as Specialized Worker

- PASS - DSH profiles are task-specific (web, headless, rescue)
- PASS - dsh-codex-taskboard is a link, not replacement
- PASS - No competing control planes (Paperclip, OpenHands, Agent Orchestrator not installed)

### Browser Automation

- PASS - Browser automation is optional, task-triggered, not mandatory

### Existing Integrations Preserved

- PASS - HyperResearch integration present (CLAUDE.md, .hyperresearch/, .claude/skills/hypersearch/)
- CONFIGURED_UNVERIFIED - Loop Engineering referenced in AGENTS.md and agent presets
- PASS - Agent skills present (.claude/skills/ 19 entries, .agents/skills/ 10 entries, skills-lock.json)

---

## F. Findings and Remediation (Ranked by Severity)

| Rank | Finding | Severity | Remediation |
|||--|--|
| 1 | rescope-vendor:check fails: 3 files reference @deepseek-ai/cordis (pre-rescope name) | HIGH | Update import paths in 3 files |
| 2 | dsh --profile web --dump-config produces empty output | HIGH | Investigate CLI output capture or rebuild via build:lib:host |
| 3 | dsh --profile headless --dump-default-config fails with module loading error | MEDIUM | Investigate missing module or path issue |
| 4 | .claude/skills symlink deleted in working tree | MEDIUM | Restore via git checkout |
| 5 | CLAUDE.md modified (181 insertions) - unreviewed | LOW | Review and commit or revert |
| 6 | DEEPSEEK_API_KEY not in environment variables | LOW | Set env var before smoke testing |
| 7 | Lint, typecheck, tests NOT verified | MEDIUM | Run with proper shell |
| 8 | Detached HEAD at tag v0.2.0-rc.2 | LOW | Checkout master if development intended |
| 9 | Uncommitted untracked files | LOW | Review and commit if appropriate |

Suspected Problems:
- AGENTS.md differs from upstream (local has webhook/ entry at line 43)
- package.json engines says node >=24 but AGENTS.md says ^22.19 || >=24 (both satisfied by v24.18.0)

---

## G. Phase-Gated Remediation Plan

### Phase 1: Restore Repository Integrity (NO APPROVAL NEEDED)
Restore .claude/skills symlink via git checkout -- .claude/skills (in DSH repo).

### Phase 2: Fix rescope-vendor Check (NO APPROVAL NEEDED)
Update 3 files with pre-rescope package name tokens (@deepseek-ai/cordis):
- packages/extensions/cordis-host-runner/tests/inspect-registry.spec.ts
- snapshots/session/cordis-inspect-liveness/client-fixture.mjs
- snapshots/session/cordis-inspect-timeout/client-fixture.mjs

### Phase 3: Fix CLI Configuration Issues (REQUIRES APPROVAL)
Investigate empty dump-config and headless profile error; may require pnpm run build:lib:host.

### Phase 4: Run Full Verification Gates (NO APPROVAL NEEDED)
Execute lint, typecheck, tests, doc sync with proper shell supporting &&.

### Phase 5: Smoke Test (REQUIRES APPROVAL)
Set DEEPSEEK_API_KEY; run dsh --profile web 'task'. Involves API cost.

---

## H. Completion Criteria

| Requirement | Evidence Needed |
||--|
| R-18 (web dump-config) | dsh --profile web --dump-config produces composed config tree |
| R-46 (hygiene) | pnpm run hygiene exits 0, all gates PASS |
| R-48 (headless profile) | dsh --profile headless --dump-default-config exits 0 with output |
| R-28 (API key) | DEEPSEEK_API_KEY set in environment or DSH credential injection verified |
| Lint/typecheck/tests | pnpm run lint, typecheck, test all exit 0 |
| Doc sync/budgets | pnpm run doc-sync and verify-doc-budgets exit 0 |

---

## I. Owner Decisions Required

1. Restore .claude/skills symlink (low risk, reversible)
2. Fix pre-rescope name tokens in 3 files
3. Rebuild DSH CLI via build:lib:host (medium risk)
4. Run full verification suite (lint, typecheck, tests, doc sync)
5. Set DEEPSEEK_API_KEY for smoke testing (API cost + authorization)
6. Review and commit CLAUDE.md changes (181 insertions)
7. Commit untracked files (.agents/skills/*, .claude/agents/, .hyperresearch/, skills-lock.json)
8. Branch management (checkout master vs stay on detached HEAD)

---

## Appendix A: AGENTS.md Comparison

| | Local (DSH repo) | Upstream (GitHub master) |
||--|--|
| File size | 17,934 chars | 17,849 chars |
| Lines | 185 | 182 |
| Last commit | 2026-09-28 (23d3807ae1) | Retrieved 2026-10-09 |
| Difference | 3 extra lines, 85 extra chars | Local has additional webhook/ entry at line 43 |

## Appendix B: Key Configuration Files

| File | Purpose | Status |
||--|--|
| AGENTS.md | Root standing orders | Present (185 lines vs upstream 182) |
| docs/AGENTS.md | Documentation standard | Present (10,761 chars) |
| docs/architecture.md | Architecture reference | Present (92 lines) |
| package.json | Project manifest | Present |
| skills-lock.json | Skills lock file | Present (10 skills tracked) |
| .dsh-build/client-build-environment.json | Build environment | DSH_CLIENT_VERSION: 0.2.0-rc.2 |
| .claude/settings.json | Claude Code settings | Present (hooks for hyperresearch) |
| .claude/skills/ | Skills directory | Present (19 entries), git-tracked symlink deleted |
| .claude/skills.old | Old symlink ref | Content: ../.agents/skills |
| .agents/skills/ | Agent skills | 10 plugin skills + skills-lock.json |
| .hyperresearch/ | HyperResearch | Present (untracked) |
| .dsh/.credentials.yaml | Credential store | 1,070 bytes, 22 lines, 10 API key references |
| profiles/web/ | Web profile config | cordis.yml, cordis.patch.yml, package.json |
| CLAUDE.md | Project instructions | 182 lines, modified (181 insertions, 1 deletion) |
