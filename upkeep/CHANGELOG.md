## Jobs

- A worker now runs jobs in three lanes at once, so a long job no longer holds up the schedule. Heals, which can run a fix agent for a long while, have a lane of their own. The quick jobs that only call APIs (`releases`, `labels`, `notifications` and `digest`) share another. The jobs that clone and push to repositories (`bump`, `drift` and `stalled-updates`) take turns in the third, so two never push to the same repository at once. Before this, a heal could leave notifications and everything else queued behind it for as long as its agent ran.
- Heal decisions are only capped when the worker's config sets `decisionsPerDay`. A worker using the `opencode` provider defaults to 300 a day.

## Dashboard

- A queued run's page shows its lane and what it's waiting for: the runs going in that lane, each linked with the worker running it, and how many are queued before it. When nothing in its lane is running, it says it's waiting for a worker to take it.
- The runs table shows which lane a queued run is waiting in, where the worker would otherwise be.

## Server

- Each job in the jobs list carries its lane.

## Internals

- The worker's status file lists every job running across its lanes, and its writes take turns.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.7...0.1.8
