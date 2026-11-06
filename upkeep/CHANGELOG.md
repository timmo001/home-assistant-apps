## Jobs

- `skill-updates` pushes the shared skills' updates that need no review straight to the default branch, with no agent: imports with no local edits, including SHA-only moves, are applied, validated with `mise run validate` and pushed, and the imports one tool release moves land together as `Update <repo> to <tag>`.
- What needs an agent, such as upstream changes to merge into a skill's local edits or a skill to review against a new tool release, starts a run of the new `skill-change` job instead of failing the run. Problems no agent can settle, such as an upstream that's gone, still fail it.
- New `skill-change` job: an agent changes a skill in its own checkout and commits once without pushing. A commit that only moves pins in `skills.yml` is pushed straight away; anything else is held on the server as a patch for your approval. Approving lands it from a fresh checkout on any worker, and one that no longer applies or validates is marked stale. Asking for changes resumes the agent's session on its own worker, or starts again from the held patch on any worker when that one is down.

## Server

- Held skill changes are kept in a new `skill_changes` table, with endpoints to list, read, keep and move them on, and to queue `skill-*` commands. A new waiting change for a skill drops the older one waiting, so each holds one.

## Settings

- `skills.updatesAgent` is gone. `skills.agent` sets the model and variant held skill changes run on, the first of `heal.agents` by default, and `skills.sessionMinutes` how long it has, 30 by default.

## Internals

- Heal's OpenCode session helpers moved into `jobs/agent.ts`, shared with the skill-change job.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.19.0...0.20.0
