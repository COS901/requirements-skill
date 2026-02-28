# Requirements Conflict Detection

The requirements maintenance workflow includes a conflict-detection gate to reduce requirement drift, overlap, and accidental breakage during add/change/remove operations.

## Command

```bash
python3 .claude/scripts/check_requirements_conflicts.py --root <requirements-root>
```

PR-focused mode:

```bash
python3 .claude/scripts/check_requirements_conflicts.py --root <requirements-root> --changed-only --range HEAD~1..HEAD
```

In this repository, the example root is `examples/saas-webapp/requirements`.

## What It Detects

- Broken relative markdown links under the chosen requirements root
- Duplicate story IDs within an area
- Duplicate story titles
- Endpoint overlap across stories (warning)
- High-similarity acceptance criteria for same endpoint (possible duplicate)
- Basic conflicting acceptance marker (`idempotent` vs `non-idempotent`)
- Missing required sections (warning)

## Handling Findings

- **Errors**: must be resolved before merging.
- **Warnings**: review and either resolve or document intentional overlap clearly in acceptance criteria.

## Required Story Sections

- `User Story`
- `Key Fields/Parameters`
- `Acceptance Criteria`
- `Evidence`
- `Linked Tickets`
