# 0210 Project Stage Transitions

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As a project owner, I can move projects through valid stages.

## Key Fields/Parameters

- `POST /api/projects/<project_id>/stage`
- fields: `from_stage`, `to_stage`, `reason`

## Acceptance Criteria

- Out-of-order stage transitions are rejected.
- Successful transitions emit audit event and updated timestamp.

## Evidence

- `tests/integration/projects/test_stage_transitions.py`

## Linked Tickets

- [TKT-004](../../../tickets/TKT-004-project-stage-guardrails.md)
