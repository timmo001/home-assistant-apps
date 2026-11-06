## Dashboard

- A new Skills page, with a count in the menu of the skill changes waiting for you. Held changes show their diff, why they started and what the agent said, with Approve, Request changes (Resume the agent or Start again on any worker), Drop and Open in Herdr, which opens an agent in the change's checkout on a worker that's up and has `attention.launch`.
- Below the changes, every skill in each repository: where it comes from (authored, imported, adapted or external), how it stands against its upstream and the tools it covers, which repositories keep a copy, and its last commits. Ask for a change starts an agent on a skill, held for approval like the rest.
- The Jobs link is only highlighted on the Jobs, job and run pages.

## Jobs

- `skill-updates` sends what it read of the shared skills repository to the Skills page after each run, and the skills of any repositories in the worker's new `skills.repos` setting.
- `skill-change` can open an agent on a held change, with a brief of where it stands.

## Server

- New `/api/skills` endpoints for the Skills page and its actions, and `PUT /api/work/skills/snapshot` for workers to send each repository's skills.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.20.0...0.21.0
