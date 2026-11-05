## Dashboard

- The inbox's kind tabs now show unread out of total, such as `Worth reading 12/65`, so you can see what's left to read in each kind at a glance.

## Jobs

- `ci` leaves dynamic runs, such as Dependabot Updates, out of a repository's CI, so a failed Dependabot run no longer marks it red or queues a heal.
- `ci` only counts active workflows, and leaves cleanup steps out of its logs.
- Bumps can update pnpm lockfiles with `CI` set.
- Checks on a clean clone run with `mise run --force`, so installs aren't skipped.

## Server

- The heal limit is now described as it works: each job gets `heals_per_day` heals for each repository, or for itself, in any 24 hours. The app option's description, the docs and the server's log messages say so.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.8...0.6.9
