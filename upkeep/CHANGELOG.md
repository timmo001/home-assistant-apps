## Jobs

- A worker's settings can now narrow the `up-*` jobs it runs. `machine.stages` lists the `dot up` stages it takes, and `machine.schedules` moves a stage to a cron of its own on that worker. A stage left out is never queued there, and its runs already queued there are dropped.
- `machine.only` makes a maintenance-only worker: it takes only the machine jobs for its stages, for a server that should keep itself current without taking Upkeep's other work.
- `machine.command` runs `dot` some other way, such as through `ssh`, so one worker can keep another machine current. The stow, Herdr and agents stages that follow a stage go through the same command.
- `machine.selfUpdate` replaces `dot up first-party` for a worker the server refuses as too old, for one installed some other way, such as through mise. Once it succeeds the worker drains and restarts on the new binary, but only once it's been up 15 minutes, so an update that brings nothing newer doesn't restart it over and over.
- The machine jobs only need `git`, so they still start while GitHub's REST API is down or the rate limit is at its reserve.

## Dashboard

- The worker list shows a maintenance-only worker as `Maintenance only`, with the stages it runs.

## Server

- The status says degraded while every live worker is maintenance-only, since nothing then runs the other jobs.
- A failure that needed you stops needing you once a later run passes and settles it. Before, it stayed in Needs you even though it showed as healed or recovered.
- A run that held a skill change for your approval stops needing you once the change lands or is dropped.
- Those already stuck in Needs you are cleared when the server starts.

## Internals

- The app image is built with the shared container image workflow, and the docs site and events Worker deploy from Alchemy stacks.
- Bun 1.4.5, Effect, Solid 2.0.3, OpenTUI, OpenCode 2, oxlint, wrangler, cronstrue, Astro and timmo001/workflows 20261116.1.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.68.0...0.69.0
