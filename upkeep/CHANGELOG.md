## Server

- Workers are told about new work as it's queued. A worker's request for work is held for up to 30 seconds and answered as soon as a run is queued for it, so a queued run starts straight away instead of on the next poll.
- Cancelling a running run stops it within moments. A worker's heartbeat is held until the next one is due and ends early when its run is cancelled.
- New `GET /api/status/changes` stream (server-sent events) says what changed as it happens: runs, logs, the inbox, attention, skills and workers.

## Dashboard

- Pages update live from the server's change stream, fetching again only what changed, and a running run's log follows as it's written. While the stream is connected, pages fall back to polling once a minute.
- A dropped stream is retried every 5 seconds, with a small "reconnecting" marker next to the version, and everything is fetched again once it's back.

## Jobs

- Bump starts each consumer as soon as it can and watches CI outside the four working slots, so a slow CI run no longer holds up the next consumer.
- Drift-review heals go straight to the hard-fix agent, skipping the decision model.
- A stalled-update heal can now close an update that another dependency's exact pin blocks, with a comment naming the pin, instead of failing.
- The dotfiles pull runs `dot up herdr` after `dot up stow`, and the Agent plugins job's description now names the plugins it updates.

## CLI

- `upkeep cancel` and the MCP `cancel` tool say the worker stops a cancelled run shortly, not at its next heartbeat.

## Internals

- No worker protocol bump: the new wait fields are optional, and older workers and servers fall back to their usual intervals.
- Updated @timmo001/docs-kit, @timmo001/groundwork-tokens and @timmo001/groundwork-ui to 0.10.2, and @timmo001/effect-gh to 0.12.0.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.27.0...0.28.0
