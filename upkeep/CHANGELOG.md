## Releases

- Releases are published by an agent now. The Publish button, its notes popover and the `release-publish` job are gone: **Release in an agent** opens one briefed with the comparison, which follows the repository's own release skill, writes the release notes from what ships rather than leaning on GitHub's generated ones, and checks the version, title and notes with you before it tags or publishes.
- **Compare all again** at the top of the Releases page reads every tracked repository afresh, so stale comparisons no longer need refreshing one at a time.

## Server

- The `POST /api/releases/:owner/:name/publish` endpoint is removed. Any `release-publish` run still waiting is cancelled on upgrade, and past ones keep their history.

## Worker

- The `publish` recipe in `releases.repos` is no longer read; it can be removed from worker config.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.45.6...0.46.0
