# requirements-skill

Open-source starter kit for maintaining product requirements with an AI-assisted workflow.

## Problem This Solves

AI-assisted teams move fast, but requirement docs often drift from code and tickets. Typical failure modes are broken links, duplicate stories, conflicting acceptance criteria, and missing traceability between requirements and implementation.

## What You Get

- A lightweight maintenance workflow for requirements-as-code
- Automated conflict detection before merge
- Changelog extraction from conventional commits for requirement history
- A concrete SaaS example tree you can copy or adapt

## Includes

- Claude agent and command for requirements maintenance (`.claude/agents`, `.claude/commands`)
- Deterministic conflict detection (`.claude/scripts/check_requirements_conflicts.py`)
- Requirements changelog extraction from conventional commits (`.claude/scripts/extract_requirements_changelog.py`)
- Example requirements tree for a typical SaaS web app (`examples/saas-webapp/`)

## Quick Start

```bash
python3 .claude/scripts/check_requirements_conflicts.py --root examples/saas-webapp/requirements
python3 .claude/scripts/extract_requirements_changelog.py --range HEAD~20..HEAD --changelog-file examples/saas-webapp/requirements/CHANGELOG.md
```

## Conventions

- One story per file (notecard scope)
- 4-digit spaced numbering for insertion-friendly ordering
- Relative links only (GitHub and local markdown viewers)
- Requirement commits use: `docs(requirements-<area>): <summary>`

## Repository Layout

- `examples/saas-webapp/requirements.md` - example requirements register
- `examples/saas-webapp/requirements/` - detailed area and story requirements
- `examples/saas-webapp/tickets/` - linked example ticket set

## License And Identity

- Code is licensed under `GPL-3.0-only` (see `LICENSE`).
- Forks for fixes and improvements are welcome.
- Redistributed copies and forks must keep copyright, license, and notice text.
- Project name and branding are reserved; see `TRADEMARKS.md`.

This combination is intended to allow collaboration while preventing forks from being presented as the official upstream project.

## Support

If you find this project useful, use the GitHub Sponsor button on the repository.
Additional tip-jar options are configured in `.github/FUNDING.yml`.
