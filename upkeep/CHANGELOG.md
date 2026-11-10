## Dashboard

- **Runs as one list:** the runs on the Jobs page and each job's page are no longer grouped by day. Folding a day away used to load every earlier day; now it's one list, newest first, that loads older runs as you scroll.
- **Date filter:** the runs' Filters sheet has a date, with Today and Yesterday a click away and any earlier day from the picker. A chosen day shows as a chip beside the search, which takes it off, and its runs load straight from the server, however long ago it was.

## Server

- **Runs by date:** `GET /api/runs` takes `since` and `until`, in milliseconds, to list the runs queued in that window.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.53.0...0.54.0
