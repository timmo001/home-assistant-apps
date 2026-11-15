## Dashboard

- Runs have their own page, Runs, beside Jobs in the menu. It has the latest runs of every job with all their filters and presets. A run's page now highlights Runs rather than Jobs. The Jobs page keeps the jobs and each worker's agents.

## Server

- A repository's drift heal that's waiting on you settles once a later drift heal for the same repository finds nothing to fix or pushes a fix. A drift review looks at all of a repository's drift as it stands, so the older question is done or out of date. It leaves Needs you and its Inbox entry goes. Ones already stuck that way are settled on upgrade.

## Jobs

- The worker reports its agents' schedules even when OpenCode can't read one session's, such as a heal session whose worktree has been cleaned up. Before, one such session hid every schedule from the run page and `upkeep schedules list`.
- An agent woken by "Ask me in the Inbox" first fetches and checks the default branch and reads the Inbox for a thread on the same work. If it's already done, it says so and dismisses the run instead of asking again.

## Internals

- Shared workflows updated to timmo001/workflows 20261115.0.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.61.0...0.62.0
