## Jobs

- Runs now ride out GitHub outages. When a run fails, the worker checks the parts of GitHub its job uses (Git, the REST and GraphQL APIs, Issues, Pull requests and Actions) with one small read each, as the run's own login. If one isn't answering, the run waits for it, checking every 2 minutes, and runs again once it's back, without using a heal. Nothing is checked before a step, so pushes are never held up.
- A run that's still waiting after 2 hours ends as the new **GitHub down** state rather than failed. It never gets a heal, the server runs it again 30 minutes later, and you can run it again from its page. A later run passing settles it like a failure.
- While a run finds the REST API down, the worker takes no new scheduled runs until it answers again. What the dashboard asks for still runs, and the worker's status reads `waiting on GitHub` with the parts it's waiting on.
- A heal whose agent can't start because GitHub's API is down waits up to 2 hours for it, and starts as soon as it's back, before queueing the job again.
- The run log says what GitHub's status page reports for the part that's down, as a hint only.

## Dashboard

- Runs that ended as GitHub down show with their own badge, and count as open failures.

## Internals

- The worker protocol is now 6, since runs can carry the new state. Update workers along with the server.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.59.3...0.60.0
