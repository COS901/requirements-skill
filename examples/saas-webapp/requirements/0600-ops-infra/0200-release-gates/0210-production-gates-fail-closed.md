# 0210 Production Gates Fail Closed

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As an engineering org, production promotions cannot proceed when required checks are missing or failed.

## Key Fields/Parameters

- required checks in deploy pipeline
- rollback trigger and verification steps

## Acceptance Criteria

- Missing required checks block promotion.
- Failed smoke tests trigger rollback flow.

## Evidence

- `.github/workflows/deploy-production.yml`

## Linked Tickets

- [TKT-010](../../../tickets/TKT-010-prod-gates-fail-closed.md)
