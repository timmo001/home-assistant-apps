## Jobs

- Unreleased, CI and Drift review run in a new **checks** lane, apart from the jobs that push to repositories, so the Releases page and CI checks no longer wait behind a long dependency or bump run.

## Server

- A run you start by hand is now taken before scheduled and event runs in its lane.
- Queuing a run for every repository takes over the runs of the same job still waiting for single repositories, in the oldest one's place, rather than running them and then checking every repository again. A manual run among them keeps it manual.

## Dashboard

- The Jobs page groups the new checks lane, and a queued run's place in its lane counts manual runs first.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.47.1...0.48.0
