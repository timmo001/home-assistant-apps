## Jobs

- **New `ci` job** (timmo001/upkeep#35): every hour it reads the latest finished run of each workflow on each tracked repository's default branch. Pull request and cancelled runs don't count. When one failed, it logs the end of the failed steps, then runs the repository's checks in a clean clone and logs how they went: whether installing changed a lockfile (so a frozen install in CI fails), whether the checks fail here too, or whether it fails only in CI. The run fails naming the red repositories, so each gets a heal. It's off for repositories already tracked until they're opted into `ci`.
- **Dismissed CI notifications:** once a workflow passes again on the default branch, the `ci` job dismisses its unread "workflow run failed" notifications.

## Heals

- A fix agent for a `ci` failure is told to tell a real failure from a CI-only one, fix the cause, push and watch CI until it passes.
- A fix agent now gets only its own repository's lines from a failed run over many repositories, rather than the end of the whole log.
- When the decision model errors, the heal now says the model couldn't choose, instead of saying there's no decision model.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.2.1...0.3.0
