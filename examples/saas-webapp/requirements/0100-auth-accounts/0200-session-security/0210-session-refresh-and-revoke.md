# 0210 Session Refresh and Revoke

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As a user, I can refresh active sessions and admins can revoke compromised sessions.

## Key Fields/Parameters

- `POST /api/auth/refresh`
- `POST /api/auth/revoke`
- identifiers: `session_id`, `user_id`

## Acceptance Criteria

- Refresh rotates tokens and invalidates old token.
- Revoke immediately blocks further API access for revoked session.

## Evidence

- `tests/integration/auth/test_session_security.py`

## Linked Tickets

- [TKT-002](../../../tickets/TKT-002-session-revocation-controls.md)
