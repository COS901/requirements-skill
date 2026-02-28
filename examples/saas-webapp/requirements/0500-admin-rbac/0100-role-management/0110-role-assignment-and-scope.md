# 0110 Role Assignment and Scope

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As an admin, I can assign roles with least-privilege scopes.

## Key Fields/Parameters

- `POST /api/admin/roles/assign`
- fields: `user_id`, `role_id`, `scope`

## Acceptance Criteria

- Unauthorized users cannot assign elevated roles.
- Role assignment changes are audit logged.

## Evidence

- `tests/integration/admin/test_role_assignment.py`

## Linked Tickets

- [TKT-009](../../../tickets/TKT-009-rbac-scope-enforcement.md)
