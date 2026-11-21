Machine jobs are named by the command they run, and three more keep servers current: containers, system packages and old files. Workers can now run from release binaries through mise.

## Jobs

- Three new machine jobs: `containers` (daily at 02:00) updates containers to their newest images and prunes old ones, `system` (02:15) upgrades system packages and removes what's no longer needed, and `clean` (02:50) removes old caches and logs. `system` and `clean` are opt-in: they only run on workers that list them in `machine.stages`. (timmo001/upkeep#109)
- Machine jobs are named `dot up <stage>` on the dashboard and in notifications, and their IDs are the bare stage: `dotfiles` rather than `up-dotfiles`, `first-party` rather than `up-first-party`, and so on. Use the new IDs with `upkeep run` and the API.

## Server

- On upgrade, the store renames `up-<stage>` to `<stage>` everywhere a job ID is kept: runs, heals, parked and paused jobs, held releases, waiting heals, inbox entries and tracked repositories. Run links keep working.
- A worker that hasn't updated yet still asks for `up-<stage>`. The server gives it those runs under the old name, so it still gets `first-party` and can update itself. This goes in a later release (timmo001/upkeep#111).

## Workers

- Each release attaches `upkeep-linux-x64` and `upkeep-linux-arm64`, built at the release's version, with `SHA256SUMS`. Machines without the Arch package can install a worker with `mise use -g github:timmo001/upkeep` and keep it current with `machine.selfUpdate`. See [Workers](https://upkeep.timmo.dev/running#workers). (timmo001/upkeep#107)

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.70.0...0.71.0
