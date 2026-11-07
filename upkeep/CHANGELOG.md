## Jobs

- A heal's "needs you" card now clears by itself once a later run of the same job gets through. For a consumer, the later run has to cover that repository without it failing; a run limited to another repository doesn't count. For Upkeep itself, the later run has to succeed. Bump heals only clear on a run for the same released repository, and a card shared by several heals goes once none of them still needs you. A fix made outside Upkeep no longer leaves a card to dismiss by hand.
- `ci` runs on the machine's login again, since it reads notifications, which a GitHub App can't.
- `deps` lists repositories through the GitHub App's installation when it runs as the App.
- Bump cleans submodules removed upstream out of checkouts it reuses.

## Dashboard

- The mode and theme controls sit beside Sign out at the end of the bar.
- Sign out is an icon button, and asks before signing you out.

## Internals

- AGENTS.md and the docs point at the open issues now that timmo001/upkeep#1 is closed.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.35.0...0.36.0
