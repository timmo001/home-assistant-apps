## Jobs

- Heals no longer message the Plannotator Inbox. A heal that's parked or left unfinished is marked as needing you on the dashboard and shows on the Attention page instead. The `heal.inbox` and `heal.inboxProject` settings are gone; old configs still load.
- Before reusing a clone, every job that keeps one removes empty Git lock files over an hour old from it and its submodules, so a Git command cut off once, such as by a restart, no longer fails every run after it.
- A heal records the directory its agent worked in, alongside its session.

## Dashboard

- A heal's run page shows its agent's OpenCode session as the `opencode2 --session` command that resumes it, with a button to copy it and **Resume in Herdr**, which opens the session on the worker that ran it, in the agent's checkout.
- Held skill changes show their agent's session the same way.

## Workers

- New `attention.resume` setting: the command a worker runs to open an agent's session, with `{session}`, `{directory}`, `{name}` and `{title}` filled in. Resume in Herdr needs it on the worker that ran the agent.

## Server

- A new `open-session` command, queued to the worker that ran the agent, and a migration adding the heal directory to runs.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.21.1...0.22.0
