# 0110 Plan Upgrade and Downgrade

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As an account admin, I can upgrade or downgrade subscription plans safely.

## Key Fields/Parameters

- `POST /api/billing/subscription/change-plan`
- fields: `workspace_id`, `target_plan`, `effective_date`

## Acceptance Criteria

- Plan changes validate eligibility and billing proration rules.
- Subscription state remains consistent across retries.

## Evidence

- `tests/integration/billing/test_plan_change.py`

## Linked Tickets

- [TKT-006](../../../tickets/TKT-006-plan-change-consistency.md)
