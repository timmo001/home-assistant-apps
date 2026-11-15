## Jobs

- `releases`, `unreleased` and `skill-updates` now run as the GitHub App rather than the machine's login, so they spend the App's rate limits and leave yours alone. They fall back to the login while the App's limits are low.
- `unreleased` reads default branches and latest releases through GraphQL in batches of 50, falling back to REST while GraphQL is the low limit.
- When a heal or change agent stops while part of GitHub it needs is down, the worker adds an OpenCode schedule to its session that checks GitHub every 5 minutes and wakes the session to carry on once it's back, for up to 2 hours.
- Heal and change agents are told they can schedule their own wake-up with `/schedule` when they have to wait for something slow, such as CI or an upstream release.

## Dashboard

- The Default, Failures and Waiting on you presets leave out heal runs whose failure has since been settled. Everything still shows them.

## Server

- A heal run now carries what settled the failure it healed, filled in for existing runs when the app updates.

## CLI

- `upkeep github check <part>...` checks parts of GitHub with the same small read a run uses, failing when one doesn't answer.

## Internals

- Updated @timmo001/oxlint-rules to 0.6.4.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.60.3...0.60.4
