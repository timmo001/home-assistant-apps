## Jobs

- **deps**: the planner now picks versions the way Renovate does. A tag pin only moves to a tag of the same precision (`v4` stays a major tag), an action pinned to a bare commit with no version comment is left alone, and a bun range resolves to the highest version in range up to `latest`.
- **deps**: Upkeep's dependency groups can be applied and pushed, behind a dry run. Repositories in `deps.apply` get their changes pushed once `deps.dryRun` is `false`; everything else is only planned.
- **deps**: closes Renovate's pull request for a group Upkeep has applied, checks for drift between repositories, and hands failed groups to heal.
- **heal**: when the agent can't start because of a GitHub rate limit, the heal waits for the limit to reset (up to an hour) and tries again. A network error or GitHub 5xx backs off 1, 2, then 4 minutes. Once an agent's session exists it's never started twice.

## Dashboard

- The run page has **Run again** (or **Heal again**) for any finished run, which takes you to the new run, and **Dismiss** when a run needs you.
- Dismissing a heal's inbox entry now clears every heal it stands for, not only the latest.

## Server

- New admin endpoints `POST /api/runs/:id/retry` and `POST /api/runs/:id/dismiss`. Retry queues the run's job again for the same release, or a heal as the same heal even when the job is parked, and dismisses the old run. It answers 409 while the run is still queued or running.

## CLI

- `upkeep retry <run>` and `upkeep dismiss <run>`, plus matching `retry` and `dismiss` agent tools.

## Internals

- A failed gh command now says why in run errors, heal records and logs: gh's stderr, or the API's message when stderr is empty, instead of a bare `GhCommandError`.
- Updated `@timmo001/effect-gh` to 0.10.1.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.11...0.7.0
