## Jobs

- Heals no longer send a message for every failure when the worker has no decision model. Those failures are recorded and left for the evening digest, so one bad stalled-updates run doesn't post a message per repository.
- A heal message, sent when a decision model leaves a failure for a person or parks a job, now quotes the log lines about its own target. For a run over many repositories, like stalled-updates or bump, that's the one consumer's failed check and the pull request it took over, not the run's list of every failure with a stack trace.
- The message says how the job goes on for that target: the next run picks a consumer up again once it's fixed, `upkeep unpark` only shows up when the job was parked, and the triage issue when there is one.
- The decision model reads the same per-target log lines, so it chooses from that consumer's failure, not the run's whole tail.

## Workers

- A worker writes its own status to `$XDG_STATE_HOME/upkeep/worker-status.json` (or `$UPKEEP_WORKER_STATUS`): a health, a one-line summary and when it was updated. The summary says what's running, how the last run ended, which jobs are parked and how many heals in the last day were left for a person. It's `warning` while something needs a person and `degraded` while the server can't be reached, so a service monitor can show more than the process being up.

## Server

- New worker endpoint `GET /work/parked` lists the parked jobs with their reason, when they were parked and their triage issue, for the worker's status.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.5...0.1.6
