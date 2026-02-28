# 0110 Email Delivery and Unsubscribe

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As a user, I receive transactional emails and can unsubscribe from non-critical email categories.

## Key Fields/Parameters

- `POST /api/notifications/email/send`
- `POST /api/notifications/email/unsubscribe`
- fields: `user_id`, `template_id`, `category`

## Acceptance Criteria

- Transactional emails bypass marketing unsubscribe list.
- Non-critical categories respect unsubscribe state.

## Evidence

- `tests/integration/notifications/test_email_preferences.py`

## Linked Tickets

- [TKT-007](../../../tickets/TKT-007-email-preference-enforcement.md)
