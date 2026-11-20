## Server

- The server can back up its store and restore it. A backup is a copy of the whole store (runs and their logs, the inbox, attention, notes, repositories, and the admin and worker tokens), made while the server runs and kept in `backups` beside the store. Restoring one checks it's a sound Upkeep store and not from a newer Upkeep, then the server starts again on it in the same process, keeping the store it replaced as `server.db.before-restore`. Settings stay where they're set. (timmo001/upkeep#110)
- Downloads go through one-time links that last five minutes, and uploads of any size are accepted.

## Dashboard

- The Jobs page has a **Backups** section: make a backup, download, delete or restore one kept on the server, or restore a file from this device. After a restore the page waits for the server and loads again.

## CLI

- `upkeep backups` lists the backups kept on the server, and `upkeep backups make`, `get <name> -o <file>`, `remove <name>` and `restore <name-or-file>` do the rest.
- `upkeep-git` now ships `upkeep-server.service`, a user unit for running the server outside Home Assistant, not enabled. It reads its settings from `~/.config/upkeep/server.env` and restarts on upgrade.

## Home Assistant app

- Home Assistant's backups of the app leave Upkeep's own kept backups out, as they're copies already.
- Uploads stream through ingress, so restoring a large backup from the sidebar dashboard doesn't sit in the Supervisor's memory.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.69.0...0.70.0
