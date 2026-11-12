## Server

- The server now stops within 3 seconds of being asked to, instead of waiting up to 20 for workers' held claims. The Supervisor gives an app 10 seconds before killing it, so every cold backup and restart was ending in "exited with non-zero exit code 137". Workers whose claim is cut short ask again on their next poll.

## Jobs

- Worktrees for two repositories whose checkouts share a folder name, such as `~/repos/notes` and `~/Documents/notes`, no longer share a run's worktree. Before, a run that updated both could commit one repository's updates to the other. The worker fix ships in `upkeep-git`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.57.0...0.57.1
