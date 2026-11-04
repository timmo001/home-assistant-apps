## Dashboard

- The overview opens with the last day in a line: how runs ended, how many commits were pushed to how many repositories, and what needs you, with links.
- A **Recent commits** list shows each commit Upkeep pushed: the repository, the linked SHA, its subject and the run that pushed it.
- The runs list has a **What it did** column and a **needs you** badge.
- A run's page shows its summary, the commits it pushed and a needs-you badge. A heal's commit links to GitHub.

## Jobs

- bump, drift, stalled-updates, ci, deps, labels, notifications and releases write a one-line summary naming the repositories they changed or failed on, and record every commit they push.
- A heal records every commit its agent pushed, with the agent's closing words as its summary.
- Heals open as named panes (job and repository) in one `Upkeep heals` Herdr workspace, not as an unnamed workspace each. A finished fix closes its pane.
- An agent ends with an outcome: fixed, nothing to fix, or needs you. Only "needs you", a stop or a timeout reaches the Inbox, and that message carries what the agent found, not the raw CI log.

## Server

- Runs carry `summary`, `changes` and `attention`. Workers report them through `POST /api/work/runs/:id/report`.
- `GET /api/activity?hours=24` returns the last day's run counts, commits and the runs that need a person.

## CLI

- An `activity` tool in MCP and Code Mode.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.3.0...0.4.0
