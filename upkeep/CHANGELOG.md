## Dashboard

- **Needs you** now keeps everything that's waiting on you until it's settled or dismissed. Before, one item stood for every heal of a job that chose the same thing, so dismissing or retrying the newest run took it away while older runs still waited. Now it moves to the next run still waiting and only goes once none is. Needs you items also no longer drop out of the inbox once they're read and old.
- A Needs you item whose agent session exists now has **Ask me in the Inbox** next to Open the run, so the agent can ask you what it needs in the Plannotator Inbox without you opening the run first.
- The inbox summary is flat and smaller, with no card behind it.
- The dashboard is now an installable web app built on Groundwork's PWA build, with its install banner and version watch. When the server is updated, the page tells you and reloads onto the new version instead of talking to the new server with old code (timmo001/upkeep#98).

## Server

- A run that isn't a heal but leaves something for you, such as an update it held back for you to check, now gets its own Needs you item. It goes once the run settles or you dismiss it.
- Unparking a job now clears the heals that parked it, so they stop showing as waiting on you.
- A one-off migration brings back the Needs you items lost to the shared-item bug, and clears parked heals for jobs that are no longer parked.
- Requests from a dashboard built for a different version get a 426, so a stale tab reloads rather than misreading the API.

## Jobs

- Release suggestions no longer count agent and editor config or git hooks as shipped: `.claude/`, `opencode.json(c)`, `hk.pkl`, `.husky/`, lefthook and pre-commit config now have impact none. Every repository is compared again with the new policy.

## Docs

- Needs you and its Ask me in the Inbox button, and which config counts as needing no release.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.60.5...0.60.6
