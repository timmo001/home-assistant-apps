## Jobs

- Heals read the last five heals of the same job and target: when each ran, what was chosen, how it ended, what it pushed and what it said. Both the decision model and the agent see them next to triage's notes, so a fix that didn't hold isn't tried again blind, and heals without triage now have a memory of their own (timmo001/upkeep#29).
- Dependency updates whose release notes the regression rules can't settle go to the decision model, as bumps already did, under the same `regression.threshold` and `regression.decisionsPerDay` cap. Each update is asked about once per run, so repositories moving a dependency between the same versions share one answer (timmo001/upkeep#90).
- The deps job reads locked versions of npm dependencies from `bun.lock`, `pnpm-lock.yaml`, `package-lock.json` and `yarn.lock`, and plans in-range lockfile updates as Renovate's `update-lockfile` and `in-range-only` strategies do. They're applied with the package manager's own update command, and under `auto` they land as their own `-lockfile` groups, including in Bun repositories, where Renovate makes none (timmo001/upkeep#77).

## Server

- A heal's `healing` response carries its earlier heals. Workers on older servers read none.

## Internals

- `@timmo001/effect-gh` is updated to 0.13.2.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.41.0...0.42.0
