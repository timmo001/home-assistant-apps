An agent can write up the inbox on request, and entries lead back to the jobs behind them.

## Dashboard

- The inbox's summary card has **Summarise in more detail**, which asks an agent for a longer write-up of what's unread and shows it in the card. The few sentences above it are still written by plain code.
- An opened inbox entry, on the inbox or a repository's page, links to the job behind it and, while it's kept, its run.
- Jobs show by their names, such as Watch, and run states, triggers and lanes are capitalised. The run page's facts line up with their labels, and a job page's Back goes to Jobs.

## Jobs

- A new `summary` job, run on request, asks the first of the worker's `heal.agents` for the write-up through OpenCode.
- Commands a worker runs get no stdin, so `opencode run` no longer waits on it.

## Server

- Inbox entries carry `runJob`, the job of their run, and workers can read the inbox from `GET /api/work/inbox`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.7...0.6.8
