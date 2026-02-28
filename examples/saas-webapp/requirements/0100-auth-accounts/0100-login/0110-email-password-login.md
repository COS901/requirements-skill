# 0110 Email/Password Login

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As a user, I can sign in with email/password and receive a valid session.

## Key Fields/Parameters

- `POST /api/auth/login`
- payload: `email`, `password`
- response: `access_token`, `refresh_token`, `expires_at`

## Acceptance Criteria

- Valid credentials produce a session token set.
- Invalid credentials fail with clear auth error and no token.
- Login events are auditable.

## Evidence

- `tests/e2e/auth/test_login.py`

## Linked Tickets

- [TKT-001](../../../tickets/TKT-001-auth-session-hardening.md)
