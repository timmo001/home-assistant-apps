## Dashboard

- An agent waiting on a permission prompt in the inbox's Needs you now shows its session, with buttons to resume it in Herdr on the machine it's waiting on, copy the `opencode2 --session` command or open it here. When the agent is a heal's, the entry also links its run.
- Table columns fit their content instead of being cut to fixed widths, and keep the widest they've been so they don't jump as the table scrolls. The wide column still takes the rest, and button columns keep their fixed width.

## Server

- Inbox entries can carry the agent session they're about. Dismissing a permission prompt's entry no longer settles the run its agent works for.

## Workers

- A drain waits 15 minutes at most: what's still running then is interrupted and put back at the front of the queue, so a long run such as a full `deps` doesn't hold up every other job. A run interrupted a second time fails.

## Internals

- Updated oxlint, @tanstack/lit-virtual, @types/semver, uv, wrangler and timmo001/workflows.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.55.0...0.56.0
