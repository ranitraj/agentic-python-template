# Changelog

All notable changes to this template will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-05-14

Initial stable release.

### Highlights

- One-shot setup wizard (`init.py`) with workflow toggles for TDD, DDD, branch protection, and GitHub Actions.
- UV-based per-service virtualenvs with direnv auto-activation.
- Strict pre-commit: ruff, mypy strict, pylint (with duplicate-code detection via `[tool.pylint.similarities]`).
- Document Driven Design (DDD) with a 5-state design-doc lifecycle, solution docs, and append-only ADRs.
- Three layers of AI guardrails for Claude Code:
  - Hooks (mechanical, always-on): pre-edit reuse reminder, stop-time `/simplify` nudge, periodic review prompt.
  - Pylint similarities (deterministic, commit-time): flags 6+ identical lines across files.
  - `/review` slash command (semantic, opt-in): orchestrates three read-only review agents (dry-reviewer, simplicity-reviewer, docs-sync) in parallel.
- GitHub Actions CI with a per-service test matrix.
- Apache 2.0 license.

### Added

- `.claude/agents/` with `dry-reviewer`, `simplicity-reviewer`, `docs-sync`, and a directory README.
- `.claude/commands/review.md` for the `/review` orchestrator.
- `.claude/DDD.md` and `.claude/TDD.md` referenced from `CLAUDE.md`.
- `.claude/solutions/README.md` and `.claude/decisions/README.md`.
- `LICENSE` (Apache 2.0).
- `init.py` opt-out compliance: when adopters decline TDD or DDD, the wizard now strips the corresponding sections from `CLAUDE.md`, removes orphan `.claude/{DDD,TDD}.md` files, and cleans up `docs-sync` references across the template.

[1.0.0]: https://github.com/ranitraj/agentic-python-template/releases/tag/v1.0.0
