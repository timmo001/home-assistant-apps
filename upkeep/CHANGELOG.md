Agents' OpenCode schedules are now visible and in your hands, finishing the schedules work in timmo001/upkeep#101.

### Dashboard

- A run with an agent session, such as a heal or a change, shows the schedules on that session: when each wakes next, any condition it waits on, how often it has woken and its last outcome.
- Pause, resume or delete a schedule from there, or add one with a prompt, a time (in, at, every or cron) and an optional shell condition. The change runs on the session's worker as a command run.

### Server

- Keeps the latest schedules each worker reports, and serves a run's at `GET /api/runs/:id/schedules`. The dashboard updates when they change.

### Worker

- Checks the schedules on its agents' recent sessions every 5 minutes and straight after each change, and tells the server when they changed.
- Carries out the new `schedule-pause`, `schedule-resume`, `schedule-delete` and `schedule-add` commands through OpenCode's schedule API.

### CLI

- `upkeep schedules list <run>`, `upkeep schedules pause|resume|delete <run> <schedule>` and `upkeep schedules add <run> "every 30 minutes" <prompt>`, with `--name` and `--condition`.
- New MCP and Code Mode operations: `schedules` (read), `schedule` and `schedule_add` (write).

### Internals

- Groundwork packages updated to 0.47.0.
- Docs cover the schedules list and the new commands.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.60.6...0.61.0
