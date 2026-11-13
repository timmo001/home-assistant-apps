## Inbox

- Updates the Dependencies, Skill updates and Stalled updates jobs push are version bumps now, grouped one entry per update across repositories like Renovate's, rather than one "worth reading" entry per commit. A skill change that only moves pins is a version bump too, and one you approved counts as yours and starts read. The existing entries are moved the same way when the server starts.
- An update that moves several packages at once, such as `Update a to 1.2, b to 1.2`, keeps one entry across versions, rather than one per release.

## Jobs

- Workers keep a tenth of GitHub's core and GraphQL rate limits for everything else on the account, such as workflows that publish with a personal token. While their login is down to that, they take no new runs, except what the dashboard asks for, until the limit resets, and their status reads `Paused for GitHub's rate limit until` the reset.
- CI runs as the GitHub App, so its reads stop spending your rate limit. Only reading and dismissing your CI notifications uses your login.
- CI no longer counts a repository red when its failed runs all ran out of GitHub's rate limit, so no heal is queued. Once the limit is back above its reserve, it runs their failed jobs again, once each, and asks for you only if they run out again.
- Jobs that push and watch CI go by how long that repository's CI usually takes, kept from the last ten passing runs of each workflow in `$XDG_CACHE_HOME/upkeep/ci-timings/`. The first look comes at about three quarters of the usual time, then one every eighth of it, and each look is a conditional request that costs no rate limit when nothing changed. Heal and change agents are told the same pace, and release agents to look at most once a minute.
- Dependencies commits new mise lock sidecars along with the updates that need them.

## Internals

- Dependency updates, including prettier 3.10.1, wrangler 4.161.0, OpenCode 2, markdownlint-cli2 0.24.1 and groundwork 0.27.0.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.57.1...0.58.0
