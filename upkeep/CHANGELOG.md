## Jobs

- **One heal for a failure across several consumers.** When a bump, or any job over repositories, fails in several consumers, the server now queues one heal over all of them instead of one per consumer. The fix agent checks them out side by side and gets `sessionMinutes` for each repository, up to four times. It finds the cause once, then runs each repository's checks and pushes each on its own. Its commits show in the inbox as one "Upkeep fixed …" entry. Heals per day still count per repository, and a repository past its limit is still held on its own.
- **New `change` job.** Ask for one change across several repositories with `upkeep change owner/a owner/b --prompt "…"`, or the `change` command at `POST /api/attention/commands`. The last of the worker's `heal.agents` makes it in one headless session over checkouts side by side, checking and pushing each repository on its own and never opening a pull request. Its commits show in the inbox as one entry named for your prompt. A failed change is never healed.

## CLI

- New `upkeep change <repo...> --prompt`.

## Internals

- The worker protocol is now 2, because heals carry a new multi-repository target. Workers on 0.28.0 or older are refused with `WorkerOutdated` until `upkeep-git` is updated.
- The heal fix's checkout and session code is now shared as `across()` in the worker, used by both heals and changes.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.28.0...0.29.0
