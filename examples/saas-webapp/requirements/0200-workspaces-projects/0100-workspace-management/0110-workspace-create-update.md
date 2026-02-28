# 0110 Workspace Create and Update

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As an admin, I can create and update workspace settings.

## Key Fields/Parameters

- `POST /api/workspaces`
- `PATCH /api/workspaces/<workspace_id>`
- fields: `name`, `plan`, `timezone`

## Acceptance Criteria

- Workspace create/update validates required fields.
- Updates are idempotent for identical payloads.

## Evidence

- `tests/integration/workspaces/test_workspace_crud.py`

## Linked Tickets

- [TKT-003](../../../tickets/TKT-003-workspace-settings-contract.md)
