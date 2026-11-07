## Jobs

- Jobs that work across repositories, such as bumps, syncs, drift, skills, deps, watch and stalled updates, can make their own GitHub calls as a GitHub App, so they count against the App's rate limit rather than your login's. Set **github_app_id** and **github_app_key** on the app, and **github_app_account** only when the App is installed on more than one account. Heals and agents keep the worker's login, and without the options every job does as before. See [Jobs as the App](https://upkeep.timmo.dev/events#jobs-as-the-app) (#55).

## CLI

- `upkeep inbox list` and `upkeep inbox move <entry> bumps|worth|upkeep`, with matching MCP tools, to read the inbox and move entries between Worth reading and Version bumps (#59).

## Internals

- Update the desktop worker only after the server is on 0.35.0.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.34.0...0.35.0
