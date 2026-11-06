## Jobs

- New machine jobs keep each worker's own machine current without running `dot up`. Each one runs a single `dot up <stage> --json` stage headless on every worker that asked for work in the last half hour:
  - `up-dotfiles` (hourly) pulls the dotfiles, rebuilds `dot` and stows them.
  - `up-skills` (hourly, ten minutes after `skill-updates`) moves the shared skills to the latest main and relinks them.
  - `up-repos` (every 30 minutes) pulls the tracked repositories that are behind and have no work in progress.
  - `up-tools` (daily at 05:10) installs and upgrades mise tools.
  - `up-plugins` (daily at 05:20) updates the agent plugins.
- When a stage changes skills or plugins, the job then runs `dot up agents` to reload running agents.
- A failed stage fails its run, which is never healed. A worker without `dot` skips the run.

## Server

- Machine jobs are queued per worker. Once a minute, the server queues a run for each live worker whose latest run of a job is older than that job's last scheduled time, so a worker that was off catches up when it comes back. A manual run queues on every live worker.

## Dashboard

- A new Machine lane in the Jobs table, whose last run column shows each worker's latest run of each machine job.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.23.0...0.24.0
