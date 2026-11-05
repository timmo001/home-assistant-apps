## Server

- A release that arrives while its job is parked or paused is held rather than dropped, keeping the latest per job and repository. Unparking the job, by hand or when its triage issue resolves, or resuming it queues what was held. Before this, a release during a parked spell never reached its consumers until it was run by hand.

## Internals

- Updates `@timmo001/groundwork-tokens` and `@timmo001/groundwork-ui` to 0.9.36.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.8.0...0.8.1
