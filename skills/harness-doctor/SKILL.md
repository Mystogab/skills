---
name: harness-doctor
description: Audit the Harness governance system for drift, contradiction, stale memory, fragmented authority, and misalignment with the actual project state.

version: 1.1.0

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

# Read

Inspect:

- `AGENTS.md`
- `.harness/**`

Especially:

- `ARCHITECTURE.md`
- `MEMORY.md`
- `CONVENTIONS.md`
- `TASKS.md`

Use repository files only as supporting context:

- `package.json`
- `tsconfig.json`
- lint/format configs
- relevant source directories
- test directories
- CI/CD config if relevant

---

# Build Mental Model

Understand:

- current architecture
- active migrations
- project conventions
- declared workflows
- intended patterns
- known technical decisions
- temporary vs permanent rules
- canonical sources of truth

Before reporting issues, build a coherent understanding of how the Harness is intended to operate.

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

Determine which file owns each type of knowledge.

Examples:

| Concern | Preferred Source |
|---|---|
| architecture | `ARCHITECTURE.md` |
| coding standards | `CONVENTIONS.md` |
| temporary project state | `MEMORY.md` |
| active work tracking | `TASKS.md` |

Flag:

- duplicated ownership
- contradictory ownership
- rules defined in multiple places
- governance fragmentation

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

- governance quality
- drift severity
- architectural clarity
- AI reliability risk
- major governance smells

---

## 2. Critical Findings

For each finding include:

- severity
- affected files
- exact paths
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

Bad:

> “Clean this section.”

Good:

> “Move import ordering rules from AGENTS.md into CONVENTIONS.md to eliminate duplicated governance authority.”

---

# Success Criteria

A successful audit should:

- reduce governance entropy
- improve AI decision consistency
- reinforce single sources of truth
- eliminate stale project memory
- improve Harness maintainability
- reduce ambiguity
- keep governance aligned with implementation reality
```
