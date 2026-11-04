Upkeep now only works on the repositories you track, rather than every repository you own (timmo001/upkeep#38). **After updating, add your repositories with `upkeep repos add owner/name`.** Until you do, the jobs that work on repositories do nothing.

## Jobs

- `releases`, `labels`, `bump`, `notifications`, `stalled-updates`, `drift` and `deps` only work on repositories tracked for them. Each run logs how many repositories are tracked for it.
- Only the releases of repositories tracked for `releases` count, and `bump` only rolls a release out to consumers tracked for `bump`.
- The worker's `deps.repos` setting is gone. Opt repositories into `deps` instead.

## Server

- The server keeps the list of tracked repositories and the jobs each one is opted into, under `/api/repos` (admins only).
- Adding a repository without naming any jobs opts it into every job that works on repositories. Naming a job that doesn't work on repositories is rejected.
- Workers read the repositories tracked for a job from `/api/work/repos`.

## CLI

- `upkeep repos add|list|remove` manages the list. `--job` opts a repository into only the jobs you name, and can be repeated.
- MCP and Code Mode gain `repos` (read), `track` and `untrack` (write).
- `upkeep run --local` reads the tracked list from the server, so it needs `--server` and an admin token.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.11...0.2.0
