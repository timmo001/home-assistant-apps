Repositories can show by names of your own.

## Dashboard

- Each repository shows by its name when it has one, then its README's title, then its own name, in the inbox, its filters and the Repositories pages.
- A repository's page has Rename, to name it by hand. Reset clears a name you set, so a worker's name or the README title shows again.

## Jobs

- `watch` can name the tracked repositories from your own list. Opt in with `names.command` in the worker's config file, a command printing a JSON array of objects with `github` and `name`, such as `dot repo list --json`. A name set by hand always stays.

## Server

- Tracked repositories have a `name` and `namedBy` (`you` or `worker`). `PATCH /api/repos/{owner}/{name}` sets or clears the name, and workers send theirs to `POST /api/work/repos/names`.

## CLI

- `upkeep repos rename owner/name "Name"` sets a name, and leaving the name out clears it. `upkeep repos list` shows each repository's name or title, and agents get a `rename` tool.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.4...0.6.5
