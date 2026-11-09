## Jobs

- Change and Skill change run in a new **agent** lane, apart from heals and from the jobs that push to repositories. A run there frees the lane as soon as its agent is going, so the next one starts straight away, while the rest of the run (waiting for the agent and recording its commits or patch) carries on beside the lane on the same worker.
- Asking an agent to ask you in the Inbox frees the command lane the same way, rather than holding it for up to 10 minutes.
- Heals keep their lane until they end, so the heal sessions setting still caps how many run at once.

## Dashboard

- The Jobs page groups the new agent lane.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.48.0...0.49.0
