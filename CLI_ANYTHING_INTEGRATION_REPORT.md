# CLI-Anything Integration Report

**Date:** 2026-10-09
**Source:** https://github.com/HKUDS/CLI-Anything
**Retrieval date:** 2026-10-09T16:30:00Z
**Status:** EVALUATED, NOT INSTALLED (requires owner approval for pip install)

---

## Executive Summary

CLI-Anything is a Python-based framework that generates CLIs for software
applications, making them agent-native. It provides a CLI-Hub package manager
for discovering, installing, and managing community-built CLIs. The framework
does NOT compete with Codex or DeepSeek Harness — it is a tool-generation and
tool-discovery capability that can be integrated as a worker layer.

**Recommendation:** PROCEED WITH CAUTION — Install in an isolated Python virtual
environment after owner approval. CLI-Anything adds genuine capability gaps
(CLI generation, CLI discovery) not covered by the current DSH setup. Integration
can be done as a DSH skill or MCP tool layer.

---

## 1. Investigation Summary

### Project Overview
- **Repository:** https://github.com/HKUDS/CLI-Anything
- **License:** Not explicitly identified (needs verification from repo)
- **Language:** Python
- **Package manager:** pip (PyPI: cli-anything-hub)
- **Latest news date:** 2026-05-30
- **Python requirement:** Python 3.12 available (confirmed: Python 3.12.0)

### CLI-Hub Package Manager

CLI-Hub is the central package manager for CLI-Anything CLIs:
- `pip install cli-anything-hub`
- `cli-hub list` — browse registry
- `cli-hub search <keyword>` — search by keyword
- `cli-hub info <name>` — inspect one CLI
- `cli-hub install <name>` — install from CLI-Hub
- `cli-hub update <name>` — update an install
- `cli-hub uninstall <name>` — remove an install
- `cli-hub launch <name> [args...]` — run an installed CLI

### Supported Applications (Sample)
- GIMP (image editing)
- Blender (3D modeling)
- Obsidian (knowledge management)
- Safari (browser automation)
- QGIS (GIS/map authoring)
- Unreal Insights (game engine profiling)
- Calibre (e-book management)
- Joplin (note-taking)
- Rekordbox (music management)
- n8n (workflow automation)
- ArcGIS Pro (GIS)
- UniMol Tools (molecular modeling)
- ExifTool (metadata)

### Architecture
- Each CLI is a Python package under the `cli_anything.*` namespace
- Uses Click CLI framework
- Each CLI has an `agent-harness/` directory with core modules, utils, tests
- Tests included (pytest-based, 134+ tests for some CLIs)
- Skill files (SKILL.md) for Claude Code integration

## 2. Suitability Assessment

| Criterion | Evaluation | Notes |
||--|--|
| Software-operation CLI generation | YES | Creates agent-native CLIs for desktop applications |
| Existing CLI discovery through CLI-Hub | YES | `cli-hub list/search/install/launch` commands |
| Structured command output | YES | JSON output from generated CLIs (per DSH conventions) |
| Application-specific capabilities | YES | 18+ apps with specific workflows |
| Testability | YES | Each CLI includes pytest tests |
| Reproducibility | YES | Pinned versions, reproducible installs |
| Compatibility | PARTIAL | Python 3.12 available; DSH is Node-based (integration overhead) |
| DSH integration without violating Codex authority | YES | CLI-Anything is a tool layer, invoked by DSH, not a control plane |
| Security | CAUTION | Requires pip install; generated commands need security review |

### Key Strengths
1. **Gap-filling**: CLI generation and discovery not currently available in DSH setup
2. **Test coverage**: Each CLI ships with comprehensive pytest tests
3. **Active development**: Regular updates in 2026-05
4. **Security hardening**: Recent passes on Sketch CLI token-file handling, CLI-Hub registry handling
5. **Skill integration**: Can be installed as a Claude Code skill via `npx skills add`

### Key Concerns
1. **Python dependency**: DSH is Node.js; CLI-Anything is Python (requires Python integration)
2. **Global pip install**: `pip install cli-anything-hub` modifies the Python environment (owner approval required)
3. **Security scope**: Generated CLIs may require filesystem/network access (sandbox implications)
4. **Not yet installed**: No execution evidence in current environment

## 3. Integration Proposal

### Integration Path
1. Install CLI-Anything in an isolated Python virtual environment (NOT global pip)
2. Verify `cli-hub list` and `cli-hub search` work
3. Identify one representative tool relevant to the existing project (e.g., Obsidian CLI for knowledge management or ExifTool for metadata)
4. Install that tool in the isolated environment
5. Configure DSH to invoke the CLI via a shell tool or MCP wrapper
6. Document the integration as a skill in .claude/skills/

### Integration with DeepSeek Harness
- DSH shell tool can invoke CLI-Anything commands via `cmd` or `bash`
- Claude Code skill (`npx skills add HKUDS/CLI-Anything --skill cli-hub-meta-skill`) can be loaded in DSH sessions
-
NoKV storage: CLI-Anything outputs can be captured as DSH session artifacts

### Codex Control Plane Preservation
- Codex remains sole orchestrator and routing authority
- CLI-Anything is invoked as a delegated worker tool, not an independent agent
- All CLI-Anything outputs are subject to Codex's review and approval

## 4. Installation Boundary

**Authorized (no owner approval needed):**
- Research and evaluation (completed)

**Requires owner approval:**
- `pip install cli-anything-hub` (global Python package installation)
- Installation of specific CLI tools (e.g., `cli-hub install gimp`)
- DSH/MCP integration configuration

## 5. Recommendation

**PROCEED WITH APPROVAL** — CLI-Anything adds genuine tool-discovery and CLI-generation
capabilities that fill a gap in the existing DSH setup. The integration is safe (tool
layer, not control plane) but requires owner approval for the pip installation step.

**Proposed first step:** Install CLI-Anything in an isolated Python venv (not global),
verify `cli-hub list`, and install one representative tool (Obsidian CLI recommended
for knowledge management integration with the existing HyperResearch setup).

---

## Appendix A: Commands That Would Be Used

```bash
# Isolated virtual environment installation
python -m venv .venv-cli-anything
.venv-cli-anything\Scripts\activate  # Windows
pip install cli-anything-hub

# Verify installation
cli-hub --version
cli-hub list

# Install a representative tool
cli-hub install obsidian
cli-hub info obsidian
cli-hub launch obsidian --help

# DSH skill installation (optional)
npx skills add HKUDS/CLI-Anything --skill cli-hub-meta-skill -g -y
```

## Appendix B: Evidence

- URL: https://github.com/HKUDS/CLI-Anything (retrieved 2026-10-09)
- PyPI: https://pypi.org/project/cli-anything-hub/ (retrieved 2026-10-09)
- README.md: 80,551 chars (fetched from GitHub raw)
- Python: 3.12.0 available
- News entries through 2026-05-30 (active development)
- 18+ supported applications documented