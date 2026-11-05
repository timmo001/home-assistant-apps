## Jobs

- **Attention**, a new job that collects the pull requests, issues and notifications that involve you from GitHub every 15 minutes, in place of the old daily brief. It sorts each one by its signals (review requested, changes requested, failing checks, conflicts, a new reply, blocked, gone quiet) with no model involved, and logs only what moved since the last run. Searches, work sites and exclusions come from the worker's `attention` config, and an optional work-time command decides the default view.

## Dashboard

- **Attention page**, grouping items by piece of work (stacks, linked issues and outside waits) into Needs you, Blocked, Going stale and Waiting on others, with Your backlog and Watching folded away. A Work, Personal or All filter defaults by work time, and items new since you last looked, on any device, are marked. Opening the page queues a fresh collection when the last one is more than 5 minutes old.
- Pages load with skeletons shaped like their content instead of a spinner.
- A request that's still retrying is no longer restarted by every 5-second poll, so a failure now shows instead of loading forever.

## Server

- Stores attention items and groups, with a shared "last looked" time, and serves them at `/api/attention`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.9.0...0.10.0
