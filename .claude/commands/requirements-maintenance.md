# Requirements Maintenance

Update and normalize project requirement docs (`<requirements-register>`, `<requirements-root>/**`) with valid links, conflict detection, evidence traceability, and changelog-ready summaries.

## Instructions

1. Use `.claude/agents/requirements-maintenance.md` workflow.
2. Confirm working paths (`<requirements-register>`, `<requirements-root>`, `<tickets-root>`).
3. Keep story docs single-behavior and maintain 4-digit numbering.
4. Run conflict detection and resolve errors:
   - `python3 .claude/scripts/check_requirements_conflicts.py --root <requirements-root>`
   - for PR deltas: `python3 .claude/scripts/check_requirements_conflicts.py --root <requirements-root> --changed-only --range HEAD~1..HEAD`
5. Repair indexes and relative links after edits.
6. Use requirements commit convention (`docs(requirements-<area>): ...`).
7. When requested, extract/apply requirements changelog updates:
   - `python3 .claude/scripts/extract_requirements_changelog.py --range HEAD~20..HEAD --changelog-file <requirements-root>/CHANGELOG.md`
   - `python3 .claude/scripts/extract_requirements_changelog.py --range HEAD~20..HEAD --changelog-file <requirements-root>/CHANGELOG.md --apply`

## Scope

$ARGUMENTS
