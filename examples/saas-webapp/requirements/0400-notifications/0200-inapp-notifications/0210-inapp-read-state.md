# 0210 In-App Read State

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As a user, I can mark notifications read and keep unread counts accurate.

## Key Fields/Parameters

- `GET /api/notifications/inapp`
- `POST /api/notifications/inapp/<id>/read`

## Acceptance Criteria

- Read/unread counters are consistent across refresh and multiple devices.

## Evidence

- `tests/e2e/notifications/test_inapp_read_state.py`

## Linked Tickets

- [TKT-008](../../../tickets/TKT-008-notification-read-state-consistency.md)
