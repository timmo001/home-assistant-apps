## Server

- A heal held back by the heal limit now waits instead of being dropped. When a repository has used its heals for the last 24 hours, its heal is stored and queued once its oldest heal is a day old, so a failed bump no longer sits until the next release. A later run of the same job that reaches the repository drops the waiting heal, as does its failed run being pruned. A paused or parked `heal` keeps it waiting.

## Dashboard

- A job's page lists the heals waiting on the heal limit, with the repository, the failed run and when it started waiting.

## Docs

- The heal limit docs and the app's `heals_per_day` option say a repository past it has its heal held rather than skipped.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.10...0.6.11
