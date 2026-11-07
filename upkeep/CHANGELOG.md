## Server

- **One status.** New `GET /api/status`: Upkeep's health (`ok`, `warning` while anything needs you, `degraded` while no worker is live), what needs you with the dashboard page for each (a heal that asked, a parked job, a skill change waiting), the parked jobs and the live workers (#89).
- **Workers older than the server get no runs.** Each claim now carries the worker's protocol, and the server refuses an older worker before handing it a run, instead of leaving the run stranded until the lost-run sweep. Update workers (`upkeep-git`) before installing this release (#88).

## CLI

- `upkeep status` shows the new status. `--json` adds the bar and footer lines, and `--bar-json` prints just the bar's `{text, tooltip, class}`, for a status bar.
- The job list moved to `upkeep jobs`.
- The `status` MCP and Code Mode tool returns the new status, and a new `jobs` tool lists the jobs.

## Docs

- A Status section on the Running page, which jobs GitHub events also start, and how workers that are older than the server are handled.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.25.0...0.26.0
