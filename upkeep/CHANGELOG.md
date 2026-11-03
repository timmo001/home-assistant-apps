## Jobs

- New `drift` job, every 6 hours, taking over from tooling-drift and its shared workflow. It finds the repositories with a `tooling.yml` at their root and checks each tool against its latest release, or its newest matching tag with `tags` or `prereleases`. The `tooling.yml` format is unchanged, so existing files work as they are.
- When a tool moved and only its pins change after its `update` command runs, the move is committed as `Update <repo> to <tag>`, pushed straight to the default branch and its CI watched. No pull requests.
- When the update changes anything else, or the tool has no `update` command, nothing is pushed for it. The run logs what to review (the tool's `review` note, the release notes and the compare link) and fails for that repository, so a heal hands the review to an agent, which records the new tag once it's done.
- `UPKEEP_DRIFT_DRY_RUN=true` logs what would be pushed without pushing or failing for reviews. Clones live in `upkeep/drift` in the XDG cache directory.

## Heals

- The Inbox only hears about a heal when there's something for you to do: a job it parked, or a fix an agent left unfinished, with the Herdr pane or `opencode2 --session` to pick it up from. Each message is an action item saying what to do and what was tried, with that target's own log lines. Everything else, including fixes an agent finished and pushed, goes in the evening digest only.
- When the decision model isn't sure what went wrong (`ask`), the last agent in the list, the one for hard fixes, works on it, rather than it waiting for a person.
- A new `"provider": "opencode"` decision model asks an LLM through OpenCode (`opencode2 run` with a `provider/model`) for the same choices, for a worker with no local decision model.
- `decisionsPerDay` in the worker's `heal` settings caps how many heals a day the decision model chooses, 10 by default, so a shared free tier keeps some room. Past the cap, heals wait for the digest.
- When the decision model fails (an error or a bad answer), the heal falls back as if there were no model, rather than failing.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.6...0.1.7
