## Dashboard

- A new **Activity** page, after Inbox, shows what happened on GitHub over the last 90 days: commits, pushes, pull requests, issues, reviews, comments and releases. It takes everyone's activity in the tracked repositories, yours anywhere, and others' reviews and comments on your issues and pull requests elsewhere. What happened on one issue or pull request is gathered under it, with its title and state, under day headings, and older groups load as you scroll. Filters narrow it by kind, repositories and who (you, bots or others), and they're kept between visits.

## Jobs

- A new `timeline` job, every 15 minutes in the quick lane, reads the events of each tracked repository and your own, and the timelines of your issues and pull requests outside the tracked repositories, for the Activity page. Every read is conditional, so what hasn't changed costs nothing.
- `watch` also adds the commits it reads to Activity.

## Server

- `GET /api/timeline` returns a page of Activity groups, newest first, with `kinds`, `repos` and `who` filters and a `before` cursor for older pages. Items older than 90 days are pruned with old runs.

## Workers

- Reloading the worker (`systemctl --user reload`) now lets it finish its runs and exit, and systemd starts it again, so an update no longer interrupts a run.

## Internals

- Updated Effect, @effect/tsgo, OpenTUI, OpenCode 2, Astro, Blume, minimatch and docker/login-action.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.54.1...0.55.0
