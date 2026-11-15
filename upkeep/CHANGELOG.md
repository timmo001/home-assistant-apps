## Jobs

- Heal and change agents now read the standing notes kept for the repositories they work on (and Upkeep's own notes when working on Upkeep), and are told how to keep new ones. A line of `Note for <owner/name>: <the note>` in what an agent says last keeps a note marked as that run's, and `Note out of date: <id>: <why>` flags one for you to keep or drop.

## Dashboard

- Each repository's page has a **Notes for agents** card, the Jobs page has one for Upkeep's notes, and the Attention page's **Agent rules** are now notes too. Add a note with an optional expiry date, edit or delete it, and see whether you or an agent wrote it, with a link to the agent's run.
- A note an agent flags as out of date shows with its reason and **Keep it** or **Delete it**, and counts under what needs you.
- The Runs, Jobs and Agents tables reach down to the bottom of the window instead of stopping at half the screen.

## Server

- One store for notes, each scoped to a repository, `upkeep` or `attention`. The attention agent's rules move into it, and the old rule endpoints are gone in favour of `/api/notes`.
- Flagged notes count toward the warning health, and the status summary says how many notes to check.
- Workers read unexpired notes from `/api/work/notes` and add or flag them for the run they hold.

## CLI

- `upkeep notes list|add|edit|delete|stale|keep`, with `--expires YYYY-MM-DD` or `never`.
- MCP and Code Mode gain `notes`, `note_add`, `note_edit`, `note_delete`, `note_stale` and `note_keep`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.62.2...0.63.0
