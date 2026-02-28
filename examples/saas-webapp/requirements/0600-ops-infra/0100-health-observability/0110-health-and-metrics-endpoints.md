# 0110 Health and Metrics Endpoints

[Requirements Home](../../0000-README.md) | [Area Overview](../0000-high-level-requirements.md)

## User Story
As platform ops, I can inspect health and metrics endpoints for fast incident triage.

## Key Fields/Parameters

- `GET /healthz`
- `GET /metrics`

## Acceptance Criteria

- Health endpoint reflects dependent service status.
- Metrics endpoint is scrapeable and stable.

## Evidence

- `tests/integration/ops/test_health_metrics.py`

## Linked Tickets

- [TKT-012](../../../tickets/TKT-012-observability-minimum-baseline.md)
