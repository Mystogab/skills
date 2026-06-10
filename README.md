# Skills

Reusable AI skills and governance workflows for software engineering projects.

---

## Repository Structure

```txt id="o4b0zd"
.
├── README.md
└── skills
    └── harness-doctor
        └── SKILL.md
```

Each skill lives in its own directory.

The main entrypoint for a skill is:

```txt id="h9wq2m"
SKILL.md
```

This allows future expansion with:

* examples
* assets
* tests
* schemas
* supporting prompts
* fixtures
* changelogs

without changing the repository structure.

---

## Philosophy

These skills are designed to improve reliability in AI-assisted software engineering workflows.

Focus areas include:

* repository governance
* architecture consistency
* convention enforcement
* documentation reliability
* workflow standardization
* long-term maintainability

---

## Included Skills

### `harness-doctor`

Audits repository governance against implementation reality.

Detects:

* governance drift
* contradictory documentation
* stale architecture docs
* duplicated conventions
* tooling mismatches
* unenforced standards

Especially useful for repositories using:

* `AGENTS.md`
* `.harness/`
* architecture/convention governance files

---

## Skill Format

Skills use Markdown with YAML frontmatter metadata.

Example:

```md id="ez5v8o"
---
name: harness-doctor
description: Audit governance and architecture consistency.
version: 1.1.0

author:
  name: Gabriel Desimone
  github: mystogab
---

# Skill Content
```

---

## Status

Experimental.

The structure and conventions in this repository are still evolving.

---

## Author

Created by Gabriel Desimone

GitHub: [Mystogab/skills](https://github.com/Mystogab/skills)
