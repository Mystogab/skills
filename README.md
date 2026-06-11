# Skills

Reusable AI skills for software engineering, repository governance, and long-term AI-assisted development workflows.

---

## Philosophy

AI-assisted development works better when projects expose clear operational context.

These skills are designed to help AI systems:

* understand repository structure
* maintain architectural consistency
* reduce governance drift
* preserve long-term project memory
* enforce conventions consistently
* improve reliability across sessions

The goal is not only better prompts, but more maintainable AI collaboration over time.

---

## Repository Structure

```txt
.
├── README.md
└── skills
    ├── harness-doctor
    │   └── SKILL.md
    └── ...
```

Each skill lives in its own directory.

The main entrypoint for a skill is:

```txt
SKILL.md
```

This structure allows future expansion per skill without changing the repository layout.

Examples:

* examples
* assets
* tests
* schemas
* fixtures
* supporting prompts
* changelogs

---

## Installation

Skills can be installed using the `skills` CLI.

List available skills:

```bash
npx skills add mystogab/skills --list
```

Install a specific skill:

```bash
npx skills add mystogab/skills --skill <name>
```

Example:

```bash
npx skills add mystogab/skills --skill harness-doctor
```

---

## Included Skills

### `harness-doctor`

Audits the Harness governance system against the actual project state.

Designed for repositories using:

* `AGENTS.md`
* `.harness/`
* architecture/convention governance workflows

Detects:

* governance drift
* stale project memory
* contradictory instructions
* fragmented sources of truth
* unenforceable conventions
* dead architectural decisions
* misleading governance patterns

Focuses on long-term AI reliability and governance consistency.

---

## Skill Format

Skills use Markdown with YAML frontmatter metadata.

Example:

```md
---
name: harness-doctor
description: Audit Harness governance consistency.
version: 1.1.0

author:
  name: Gabriel Desimone
  github: mystogab
---

# Skill Content
```

---

## Status

Experimental and evolving.

The repository structure, conventions, and governance patterns may continue to change as the ecosystem matures.

---

## Author

Created by Gabriel Desimone.

GitHub: [Mystogab/skills](https://github.com/Mystogab/skills?utm_source=chatgpt.com)
