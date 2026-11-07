## Jobs

- **Drift review.** A new on-demand `drift-review` job checks each repository as a whole against the current release of every tool in its `tooling.yml`, for what it's still missing rather than only what changed since the last review: features, commands, flags and config options it doesn't cover yet, and snapshots that no longer match. Each repository with tools is handed to an agent through a heal, with a brief for the job, and finding nothing missing counts as nothing to fix. It has no schedule, so its findings never repeat on their own. Run it with `upkeep run drift-review`, or `--repo owner/name` for one repository. It works on the repositories tracked for `drift` and has no opt-in of its own (#37).

## Server

- A job can borrow another job's tracked repositories with the new `trackedAs` field, which narrowing a run to a repository honours.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.26.1...0.27.0
