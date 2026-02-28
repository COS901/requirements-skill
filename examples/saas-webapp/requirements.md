# Requirements Register

Detailed per-area requirements live in [requirements/0000-README.md](requirements/0000-README.md).

## Navigation

- [Requirements Architecture](requirements/0000-README.md)
- [Requirements Changelog](requirements/CHANGELOG.md)
- [Auth & Accounts](requirements/0100-auth-accounts/0000-high-level-requirements.md)
- [Workspaces & Projects](requirements/0200-workspaces-projects/0000-high-level-requirements.md)
- [Billing & Subscriptions](requirements/0300-billing-subscriptions/0000-high-level-requirements.md)
- [Notifications](requirements/0400-notifications/0000-high-level-requirements.md)
- [Admin & RBAC](requirements/0500-admin-rbac/0000-high-level-requirements.md)
- [Ops & Infra](requirements/0600-ops-infra/0000-high-level-requirements.md)

## Sample Register

| Req ID | Requirement | Acceptance Evidence | Success Metric | Linked Tickets | Status |
|---|---|---|---|---|---|
| AUTH-REQ-001 | Users can sign in and manage sessions securely | `tests/e2e/auth/*` | Login success rate >= 99.5% | [TKT-001](tickets/TKT-001-auth-session-hardening.md) | Proposed |
| BILLING-REQ-001 | Webhook processing is idempotent and auditable | `tests/integration/billing/test_webhooks.py` | Duplicate webhook side effects = 0 | [TKT-005](tickets/TKT-005-billing-webhook-idempotency.md) | Proposed |
| PLATFORM-REQ-001 | Production rollout gates fail closed | `.github/workflows/deploy-production.yml` | False-green deploy gates = 0 | [TKT-010](tickets/TKT-010-prod-gates-fail-closed.md) | Proposed |
