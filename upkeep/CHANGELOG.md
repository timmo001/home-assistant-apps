## Jobs

- Ci retries a failed read of a repository's CI, and leaves that repository out of the count rather than counting it red.

## Server

- A manual run of a job that runs on releases, such as Bump, now needs a release. Queueing one without it is refused with a clear error, instead of queueing a run that's bound to fail.

## Dashboard

- Jobs that run on releases no longer show a Run button, since it couldn't give them a release. Queue one with `upkeep run bump --release owner/name@tag`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.9...0.6.10
