## Dashboard

- The Jobs page has an Agents section: each worker's decision model and fix agents, with their model, variant, role and what each is for, so you can see which model would take a fix before one happens.
- A heal's run page shows the decision model that chose, on its own line, or that the fallback chose without one.
- A summary run's page shows the model and variant that wrote it.

## Server

- Workers send their agents when they ask for work, and `GET /api/jobs/agents` lists them.
- Heals record `decidedBy`, and summary runs record their `agent`. Older heals have `decidedBy` filled in from their reason.

## Worker

- Sends its decision model and agents with each claim, and reports the decision model on a heal and the agent on a summary run. Update the worker after the server, since it reads the new run fields.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.8.1...0.9.0
