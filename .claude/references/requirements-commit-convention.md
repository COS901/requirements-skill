# Requirements Commit + Changelog Convention

## Commit Subject

Use conventional commits with requirements scope:

```text
docs(requirements-<area>): <summary>
```

Where `<area>` aligns to requirements folders when possible.
In this repository's example tree, areas are:

- `0100-auth-accounts`
- `0200-workspaces-projects`
- `0300-billing-subscriptions`
- `0400-notifications`
- `0500-admin-rbac`
- `0600-ops-infra`

## Commit Body Footers

Preferred footers for extraction:

- `Req-Refs: <comma-separated requirement ids/files>`
- `Changelog: requirements`
- `Req-Summary: <single sentence for changelog>`

Example:

```text
docs(requirements-0300): add webhook retry expectation for duplicate events

Req-Refs: 0210-webhook-idempotency-and-replay.md
Changelog: requirements
Req-Summary: Added explicit retry and duplicate-event handling expectations for billing webhooks.
```

## Changelog Output Mapping

The extraction script maps commit types to sections:

- `feat` -> `Added`
- `fix` -> `Fixed`
- `docs`, `chore`, `refactor`, `test` -> `Changed`

If `Req-Summary` is present, it is used as the changelog bullet text.
Otherwise the subject summary is used.

## Good Practices

- Keep summary outcome-focused, not activity-focused.
- Include user-visible intent (what behavior/expectation changed).
- Keep one logical requirement change per commit when possible.
- Always include `Req-Refs` for traceability.
