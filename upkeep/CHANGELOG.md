## Jobs

- **New `renovate` job, hourly.** It takes over open Renovate pull requests that stalled because their checks failed. Each update is squashed onto a clean clone of the default branch, its dependencies installed, and the repository's checks run. It's then pushed straight to the default branch, the pull request is closed with a comment linking the commit, and the commit's CI is watched.
- **What it leaves to Renovate:** drafts, forks, archived repositories, pull requests into other branches, abandoned updates and Renovate's onboarding. It also leaves pull requests whose checks pass or are still running.
- **When a repository fails:** the others carry on, and the run fails at the end naming the ones that failed. Each gets its own heal, and the heal's agent is told to apply the update, migrate whatever the new version needs, push and close the pull request.
- **Dry runs:** set `UPKEEP_RENOVATE_DRY_RUN=true` on a worker to log what would be pushed without committing. Clones are kept in `upkeep/renovate` in the XDG cache directory, apart from the `bump` job's.

## CLI

- The CLI reads `UPKEEP_SERVER` and `UPKEEP_ADMIN_TOKEN` from `admin.env` in `$XDG_CONFIG_HOME/upkeep` when the environment doesn't set them, so the MCP server and OpenCode plugin find the server however they're started. The environment still wins.

## Internals

- The `bump` job's checkout, install, check, commit-and-push and CI watch helpers are shared, so `renovate` runs updates exactly as a bump does.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.3...0.1.4
