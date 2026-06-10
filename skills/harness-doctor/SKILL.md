---
name: harness-doctor
description: Audit AGENTS.md, .harness/, and the repository for governance drift, contradictions, stale documentation, and architecture inconsistencies.

version: 1.0.0

author:
  name: Gabriel Desimone
  github: mystogab

license: MIT

tags:
  - governance
  - audit
  - architecture
  - conventions
---

# Harness Doctor

Audit repository governance against implementation reality.

Read-only unless the user explicitly requests fixes.

## Read

Inspect:

- `AGENTS.md`
- `.harness/**`
- `package.json`
- `tsconfig.json`
- lint/format configs
- relevant source directories
- test directories
- CI/CD config if present

## Validate

Cross-check governance docs against the actual repository.

Detect:

- contradictory instructions
- stale documentation
- undocumented architecture changes
- dead conventions
- duplicated governance rules
- outdated migration notes
- tooling/docs mismatches
- impossible-to-enforce conventions
- completed tasks without implementation

## Repository Reality Checks

Validate:

- documented directory structure
- package/tooling references
- scripts and workflows
- testing conventions
- architecture diagrams
- task completion claims

Never assume documentation is correct.

## Report Format

### 1. Executive Summary

Summarize:

- governance health
- drift severity
- documentation quality
- major risks

### 2. Findings

For each finding include:

- severity
- affected files
- exact paths
- line references when possible
- impact
- recommended fix

### 3. Recommendations

| # | Area | Recommendation | Priority |
|---|---|---|---|

Priority:

- 🔴 High → incorrect technical decisions
- 🟡 Medium → confusion or governance erosion
- 🟢 Low → cleanup/cosmetic

## Constraints

- Never modify files automatically.
- Never invent repository structure.
- Always inspect before concluding.
- Prefer exact paths and references.
- Keep recommendations concrete and actionable.
```
