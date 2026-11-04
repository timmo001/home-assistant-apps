## Jobs

- Jobs can be paused and resumed without stopping the server or worker. A paused job isn't queued on its schedule, on releases or as a heal, and waiting runs of it stay untaken, though it can still be run by hand. Pausing `heal` stops every heal.
- Heal agents now run headless with `opencode run --auto`, named for the job and repository, instead of opening Herdr panes on the desktop. A heal that needs you names the session to pick it up from in its Inbox message.

## Dashboard

- Each job has a Pause or Resume button, and a paused job shows when and by whom it was paused.

## CLI

- `upkeep pause <job>` and `upkeep resume <job>`, with matching `pause` and `resume` MCP and Code Mode tools.

## Server

- New `PUT` and `DELETE /api/jobs/:id/pause` endpoints, and job status includes `paused`.

## Worker

- The worker's status for service monitors stays ok unless it can't reach the server. Parked jobs, heals asking for you and failed runs are still in its summary and on the dashboard, but no longer make it a warning.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.4.0...0.5.0
