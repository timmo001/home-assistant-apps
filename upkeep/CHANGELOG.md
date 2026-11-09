## Dashboard

- Your own doing no longer fills **Worth reading**. Your commits and the releases of your repositories are left out of the tab, its counts, the unread count in the menu and the repositories page, and stay under their own **Commits** and **Releases** tabs. A release Upkeep had to fix something for is still worth reading, and so is anything of yours moved there from its Move menu or by a repository rule.
- The Move menu no longer ticks **Worth reading** for an entry that isn't shown there.

## Server

- A release of one of your repositories is yours, like your own commits: it starts read, and the bumps Upkeep rolls it out with no longer bring it back unread. A fix Upkeep pushes for it still does. Releases already in the inbox are marked yours.

## CLI

- `upkeep inbox list` shows your own commits and releases as `yours`, apart from what's worth reading and the version bumps. The MCP `inbox` tool says what `you` means for it.

## Jobs

- Changes for a release resolve Bun lockfile packages past their scopes and from workspaces.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.46.0...0.46.1
