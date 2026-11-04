The dashboard is rebuilt around the inbox, with a page for each repository and tables that group and sort.

## Dashboard

- The header has the Upkeep brand, then Inbox, Repositories and Jobs, then a mode picker (auto, light, dark or darker) and Sign out last. The mode is picked before the page draws, so it never flashes the wrong one. Text is set in Inter, and code in Geist Mono.
- The inbox's feed sums up what changed in each entry rather than naming it, shows each repository by its title, and only draws the entries on screen, so it stays quick however long it gets.
- Kinds are tabs over the feed, each with its count and an explanation under it. "Routine" is now "Version bumps". On a phone the tabs scroll sideways on one line.
- The other filters sit in a sheet opened from the Filters button: read or unread, and which repositories, each a list to tick with counts and a search. Each filter that's on shows as a chip that takes it off.
- A new Repositories page lists every tracked repository, and each has a page of its own with what changed in it.
- The Jobs page's tables sort by a header press. Jobs are grouped by the lane they run in, and the latest runs by the day they were queued, under headings that fold away.

## Internals

- The dashboard is on groundwork 0.9.35, for its `gw-filter` and `gw-table`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.3...0.6.4
