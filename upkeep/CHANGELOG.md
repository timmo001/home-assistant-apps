## Dashboard

- The inbox groups every version of the same update into one entry, such as "Update Upkeep" with each version it moved to as an item, rather than an entry per version. Existing entries are merged when the server starts.
- The line above the agent's summary names what it covers, such as "An agent summarised the last 7 days, from 29 October to 5 November, 2 minutes ago", or the unread entries and their dates.

## Jobs

- `summary` gives the agent the dates it covers and whether they're the unread entries or the last 7 days, and has it name that period first rather than writing "this week". The period is recorded on the run.

## Server

- Runs carry a `period`, the stretch of the inbox a summary covers. The server and the summary job share one inbox window, `inboxDays`, so they can't drift apart.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.7.2...0.8.0
