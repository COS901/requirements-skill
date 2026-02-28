# 0210 Audit Log Access Controls

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As a compliance admin, I can access audit logs based on explicit permissions.

## Key Fields/Parameters

- `GET /api/admin/audit-logs`
- filters: `actor`, `event_type`, `date_range`

## Acceptance Criteria

- Audit logs are restricted to authorized roles.
- Access attempts are logged.

## Evidence

- `tests/integration/admin/test_audit_log_permissions.py`

## Linked Tickets

- [TKT-011](../../../tickets/TKT-011-audit-log-access-boundaries.md)
