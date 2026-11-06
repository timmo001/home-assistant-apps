## Heals

- When a heal ends needing you, the worker can run a hand-off command of your own, set as `heal.handOff.command`, in the agent's checkout, with `{session}`, `{directory}`, `{name}` and `{title}` filled in.
- A heal's session is now shared with the server when it ends needing you, so every worker with `attention.resume` shows a **Resume in Herdr** button on the run page. A worker that doesn't have the session imports it into its own checkout first.

## Dashboard

- Every session shown, from heals and skill changes, has an **Open here** link (`upkeep://open/<session>`) that opens it on the machine the browser is on.

## CLI

- `upkeep open <session>`, also run from `upkeep://open/...` links, opens a session through this machine's `attention.resume`. If the session ran elsewhere, it imports it from the server first.
- The `upkeep-git` package registers `upkeep-open.desktop` as the `x-scheme-handler/upkeep` handler.

## Server

- `GET /api/sessions/:id` returns a shared session, and workers can share one with `PUT /api/work/runs/:id/session`. Shared sessions are pruned along with their runs.

## Jobs

- Landing clean skill imports regenerates the skills catalogue, so the marketplace doesn't keep stale pins.
- Agent skill changes that only move pins in `skills.yml` and the generated marketplace land without review.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.22.0...0.23.0
