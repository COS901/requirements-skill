---
name: requirements-maintenance
description: Maintain product requirements docs as source-of-truth artifacts, including story decomposition, link hygiene, conflict detection, and changelog-ready summaries. Use when adding/changing/removing requirements, fixing requirement drift, or preparing requirements-focused commit summaries.
metadata:
  short-description: Maintain requirements docs with conflict checks
---

# Requirements Maintenance

Use this skill to keep requirements docs coherent, navigable, and aligned with implementation evidence.

## When To Use

- Add or revise requirement stories
- Break down vague requirements into single-behavior stories
- Repair relative links between requirements and tickets
- Detect overlap, duplication, and contradictions before merge
- Prepare requirement changelog summaries from conventional commits

## Path Setup

Choose paths before editing:

- `<requirements-register>`: top-level register markdown
- `<requirements-root>`: requirements tree root
- `<tickets-root>`: ticket folder linked by requirement stories

For this repository's example:

- `<requirements-register>`: `examples/saas-webapp/requirements.md`
- `<requirements-root>`: `examples/saas-webapp/requirements`
- `<tickets-root>`: `examples/saas-webapp/tickets`

## Workflow

1. Identify impacted area folder(s) in `<requirements-root>/`.
2. Edit story files first (smallest unit, one behavior each).
3. Refresh area indexes and navigation links.
4. Run conflict detection gate.
5. Resolve errors; document intentional overlap when warnings are expected.
6. Update changelog content when requested.
7. Provide commit-ready requirement summaries with traceable refs.

## Authoring Rules

- Preserve 4-digit spaced numbering (`0110`, `0120`, ...).
- Keep one behavior per story file.
- Include these sections in each story:
  - `User Story`
  - `Key Fields/Parameters`
  - `Acceptance Criteria`
  - `Evidence`
  - `Linked Tickets`

## Command Gate

Run conflict detection:

```bash
python3 .claude/scripts/check_requirements_conflicts.py --root <requirements-root>
```

PR-focused mode:

```bash
python3 .claude/scripts/check_requirements_conflicts.py --root <requirements-root> --changed-only --range HEAD~1..HEAD
```

Generate changelog snippet:

```bash
python3 .claude/scripts/extract_requirements_changelog.py --range HEAD --changelog-file <requirements-root>/CHANGELOG.md
```

Apply changelog snippet:

```bash
python3 .claude/scripts/extract_requirements_changelog.py --range HEAD --changelog-file <requirements-root>/CHANGELOG.md --apply
```

## Commit Convention

Use conventional commit subject:

```text
docs(requirements-<area>): <short requirement summary>
```

Recommended footers:

```text
Req-Refs: <ids/files>
Changelog: requirements
Req-Summary: <single sentence>
```
