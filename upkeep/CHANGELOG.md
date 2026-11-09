## Jobs

- New `up-first-party` machine job. It runs `dot up first-party` on every live worker, which upgrades the packages from the signed first-party Arch repository with no password prompt. Each package's own install script restarts its user service, and anything whose main process is still on a replaced binary is restarted after it. It runs hourly as a catch-up.
- A successful `Publish package` run in `arch-repo` now queues `up-first-party` on every worker within seconds, through the GitHub events queue. Other workflows there still queue only `ci`.

## Server

- A GitHub event that asks for a machine job queues it on every live worker, as its schedule does.

## Workers

- A worker that the server refuses as older than itself now runs `dot up first-party` itself, at most every 15 minutes, until the upgrade restarts it on a version the server accepts. Before, it waited until someone updated `upkeep-git` by hand.

## Internals

- Dropped the rules in AGENTS.md that new work gets its own issue and that public work is tracked in issues.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.49.0...0.50.0
