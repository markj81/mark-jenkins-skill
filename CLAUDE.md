# CLAUDE.md — AI Assistant Guide for mark-jenkins-skill

## Project Overview

This repository defines a **Claude Code Skill** for Mark Jenkins — a design leadership professional with 20+ years of experience. The skill surfaces Mark's expertise through Claude AI when users ask about design leadership, UX, team building, and career guidance.

This is a **documentation-only project**: there is no source code, build system, or test suite. The entire skill is expressed in `SKILL.md`.

---

## Repository Structure

```
mark-jenkins-skill/
├── CLAUDE.md       ← This file (AI assistant guide)
├── README.md       ← Brief project description
└── SKILL.md        ← The skill definition (primary file)
```

---

## Primary File: SKILL.md

`SKILL.md` is the only file that matters for the skill's behavior. It contains:

- **YAML frontmatter** (lines 1–6): Skill metadata consumed by the Claude Code platform
- **Markdown body** (lines 8–71): Content surfaced to users when the skill is invoked

### YAML Frontmatter Fields

| Field | Value | Purpose |
|-------|-------|---------|
| `name` | `mark-jenkins` | Unique skill identifier |
| `description` | Trigger phrase list + use-case summary | Tells Claude when to invoke the skill |
| `disable-model-invocation` | `true` | Skill returns content directly; does not call another model |
| `version` | `1.0.0` | Semantic version of the skill |

### Skill Trigger Phrases

The skill activates when users reference any of:
- "Mark Jenkins"
- "the design leader"
- "portfolio"
- "design systems"
- "design leadership"
- "hiring designers"
- design career advice queries

---

## Content Sections in SKILL.md

1. **About Mark** — Professional background summary
2. **Core Expertise Areas** — Six domains:
   - Design Systems & Design Ops
   - User Research & Usability
   - Team Leadership, Hiring & Mentoring
   - Prototyping & Interaction Design
   - Product Strategy & Roadmap
   - Cross-Functional Collaboration
3. **How to Use This Skill** — Four engagement modes:
   - Design Challenges
   - Work Review & Feedback
   - Leadership & Management
   - Career Guidance
4. **Contact Information** — Email and LinkedIn

---

## Development Workflows

### Making Changes

All changes to the skill's behavior require editing `SKILL.md`. There is no build step — edits take effect as soon as the file is committed and pushed.

**Common tasks:**
- Update expertise descriptions → edit the relevant section in `SKILL.md`
- Add new trigger phrases → extend the `description` field in the YAML frontmatter
- Update contact info → edit the Contact Information section
- Bump version after significant changes → update the `version` field in frontmatter

### Branch Strategy

- **`master`** — the stable upstream branch
- **`claude/*`** — branches used by AI assistants for automated changes (follow the naming pattern `claude/<description>-<session-id>`)

### Committing and Pushing

```bash
git add SKILL.md
git commit -m "Brief description of what changed"
git push -u origin <branch-name>
```

Branch names for AI-generated changes must start with `claude/`.

---

## Conventions

- **No trailing whitespace** in Markdown files
- **YAML frontmatter** must remain valid YAML; test with a YAML linter if uncertain
- **Markdown headings**: Use `##` for top-level sections, `###` for subsections — do not skip levels
- **Version field**: Follow [Semantic Versioning](https://semver.org/) — increment patch for copy edits, minor for new sections, major for structural redesigns
- **Tone**: Professional, confident, and approachable — matches Mark's personal brand as a senior design leader

---

## What NOT to Do

- Do not add source code, package.json, or build tooling — this is intentionally a documentation-only skill
- Do not create a `.gitignore` unless binary/generated files are added
- Do not rename `SKILL.md` — the Claude Code platform expects this filename
- Do not remove the YAML frontmatter block or alter its delimiters (`---`)
- Do not add CI/CD pipelines unless a testing/validation step is explicitly requested

---

## Contact

For questions about the skill's content, contact the skill owner:

- **Email**: mark@theluckystrike.co.uk
- **LinkedIn**: https://www.linkedin.com/in/markjenkins1981/
