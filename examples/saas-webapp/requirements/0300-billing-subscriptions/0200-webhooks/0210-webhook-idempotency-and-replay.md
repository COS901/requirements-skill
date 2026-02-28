# 0210 Webhook Idempotency and Replay

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As platform ops, billing webhooks can be replayed safely without duplicate side effects.

## Key Fields/Parameters

- `POST /api/billing/webhooks/provider`
- fields: `event_id`, `event_type`, `signature`
- replay store key: `event_id`

## Acceptance Criteria

- Duplicate events are deduplicated by immutable event id.
- Replay processing is idempotent.

## Evidence

- `tests/integration/billing/test_webhooks.py`

## Linked Tickets

- [TKT-005](../../../tickets/TKT-005-billing-webhook-idempotency.md)
