---
name: harness-doctor
description: Audit the Harness governance system for drift, contradiction, stale memory, fragmented authority, and misalignment with the actual project state.

version: 1.2.0

author:
  name: Gabriel Desimone
  github: mystogab

license: MIT

tags:
  - harness
  - governance
  - architecture
  - conventions
  - memory
  - audit
  - drift-detection
---

# Harness Doctor

Audit the Harness governance system against the actual state of the project.

The goal is to improve long-term AI reliability by detecting:

- governance drift
- contradictory instructions
- stale project memory
- fragmented sources of truth
- dead architectural decisions
- unenforceable conventions
- misleading or ambiguous guidance

Read-only unless the user explicitly requests fixes.

---

# Core Principle

The Harness is the operational memory and governance layer of the project.

If governance files diverge from each other or from implementation reality, the divergence must be surfaced explicitly.

The objective is not only repository correctness, but long-term cognitive consistency for AI-assisted development.

---

# Discover Governance Files

Identify the actual governance layer by scanning for common patterns. The Harness may live anywhere — look everywhere before concluding.

## Likely Locations

- Repository root (`.md`, `.txt` files with governance keywords)
- `.harness/`, `/.harness/` directories
- `docs/`, `governance/`, `conventions/`, `architecture/` directories
- Any nested directory matching common governance names

## Files to Detect by Keyword in Name or Path

| Concern | Typical Names (look for any) |
|---|---|
| architecture | `ARCHITECTURE.md`, `architecture.md`, `design.md` |
| conventions | `CONVENTIONS.md`, `conventions.md`, `standards.md`, `styleguide.md`, `coding-std*.md` |
| memory / state | `MEMORY.md`, `memory.md`, `state.md`, `project-memory.md` |
| tasks / tracking | `TASKS.md`, `tasks.md`, `backlog.md`, `active-work.md` |
| agent directives | `AGENTS.md`, `agent*.md`, `.ai/**` |

## Discovery Strategy

1. Scan root-level markdown files for governance keywords in their filename or first section heading.
2. Search common directories (`.harness/`, `docs/`, etc.).
3. Build a map of what was actually found and treat that as the authoritative harness structure — ignore templates, just use what's there.

Use repository config files only as supporting context:

- lockfiles and manifest files (`package.json`, `pyproject.toml`, `Cargo.toml`, etc.)
- tsconfig, compiler configs, lint/format configs
- relevant source directories
- test directories
- CI/CD config if relevant

---

# Build Mental Model

Understand:

- current architecture **as documented in the discovered files**
- active migrations
- project conventions
- declared workflows
- intended patterns
- known technical decisions
- temporary vs permanent rules
- canonical sources of truth

Before reporting issues, build a coherent understanding of how the Harness is intended to operate. If no governance files are found, report that explicitly as a high-priority finding.

---

# Detect Governance Drift

Detect cases where the Harness no longer reflects the real state of the project.

Examples:

- completed migrations still treated as active
- outdated architecture diagrams
- dead conventions still documented
- stale TODOs or temporary notes
- implementation patterns differing from documented standards

---

# Detect Governance Smells

Detect structural governance problems.

Examples:

- duplicated authority across files
- conflicting instructions
- ambiguous guidance
- overloaded `AGENTS.md`
- multiple competing sources of truth
- conventions that cannot realistically be enforced
- checklist-driven memory replacing architectural clarity
- vague wording that weakens decision consistency

Flag anything likely to confuse future AI sessions.

---

# Validate Sources of Truth

Determine which file owns each type of knowledge. The map discovered during the scan phase is your reference.

For each concern domain (architecture, conventions, memory, tasks, etc.), identify:

- **Which file declares authority** — explicit or implicit ownership in headings, prose, or content
- **Whether that file actually exists** — a missing file with references to it is itself a drift signal

Flag any of these conditions:

| Concern | What to Check |
|---|---|
| duplicated authority | same rule stated in 2+ files without explicit reference links between them |
| contradictory ownership | two files make incompatible claims about the same concern |
| orphaned references | a file points to another file that doesn't exist or lives elsewhere |
| governance fragmentation | any single concern split across multiple undocumented locations |

The specific filenames matter less than whether there is one clear owner per domain.

---

# Repository Reality Checks

Cross-check governance claims against implementation reality.

Validate:

- directory structure
- tooling references
- workflows
- task completion claims
- testing conventions
- architectural patterns

Never assume documentation is correct.

Implementation reality matters.

---

# Report Format

## 1. Harness Health Summary

Summarize:

- what governance files were discovered (list actual paths found)
- governance quality
- drift severity
- architectural clarity
- AI reliability risk
- major governance smells

---

## 2. Critical Findings

For each finding include:

- severity
- affected files and exact paths
- line references when possible
- why it matters
- likely AI failure mode
- recommended correction

---

## 3. Governance Smells

List structural governance weaknesses reducing long-term maintainability or AI consistency.

---

## 4. Recommended Improvements

| # | Area | Recommendation | Priority |
|---|---|---|---|

Priority:

- 🔴 High → likely to cause incorrect AI decisions
- 🟡 Medium → causes confusion or governance erosion
- 🟢 Low → cleanup or maintainability improvement

---

# Constraints

- Never modify files automatically.
- Never invent repository structure.
- Never assume governance files are correct.
- Always inspect before concluding.
- Prefer exact paths and references.
- Keep recommendations concrete and actionable.

Do not assume a specific filename pattern — the harness may use any naming convention or directory layout. Validate by detecting what's actually present, not what your expectations dictate.

Bad:

> "Clean this section."

Good:

> "Move import ordering rules from <detected-file-a> into <detected-file-b> to eliminate duplicated governance authority."

---

# Success Criteria

A successful audit should:

- reduce governance entropy
- improve AI decision consistency
- reinforce single sources of truth regardless of naming convention
- eliminate stale project memory
- improve Harness maintainability
- work with any valid harness layout, not just a specific template
```
