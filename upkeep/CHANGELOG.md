## Server

- **GitHub events.** The server can pull GitHub's `release`, `push` and `workflow_run` events from a Cloudflare Queue, filled by the new events Worker behind a GitHub App's webhook. It records each delivery once and acks it after. Set the new `events_account_id`, `events_queue_id` and `events_token` options to turn it on; without them nothing changes. Setup is on the new [GitHub events](https://upkeep.timmo.dev/events) docs page (#82).
- **Release events queue bumps.** A published release goes through the same path as the `releases` job's report, so `bump` starts seconds after a release rather than up to 30 minutes later, and the scheduled check doesn't queue it twice (#86).
- **Push and workflow run events start repository jobs.** A push to the default branch queues `watch` and `sync` for the repository, plus `deps` or `drift` when it changes the Renovate config or `tooling.yml`. A push to groundwork syncs every app, and one to the skills repository runs `skill-consumers`. A completed workflow run on the default branch queues `ci`. Only jobs the repository is tracked for run, and a burst of pushes queues one run (#84).
- Runs started by an event show the new `event` trigger.

## Jobs

- **Runs for one repository.** A run can be narrowed to one tracked repository, and every job that works on repositories then only touches that one. A waiting run for it, or for every repository, is reused. Retrying keeps the narrowing (#83).
- `drift` ends as skipped when nothing moved.

## CLI

- `upkeep run <job> --repo owner/name`, and `repo` on the `run` MCP and Code Mode tool (#83).

## Dashboard

- The runs table's Release column is now **For**, showing the release or the one repository a run was narrowed to.

## Internals

- New `packages/events` Cloudflare Worker, deployed at events.upkeep.timmo.dev.
- The event-to-job mapping and the Renovate and `tooling.yml` file names are shared from `@upkeep/api`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.24.0...0.25.0
