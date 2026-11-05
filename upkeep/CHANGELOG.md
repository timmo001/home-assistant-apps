## Dashboard

- **Refresh** on the Attention page is disabled while a refresh would collect nothing, within 5 minutes of the last collection, and says how long is left. Before, a click in that window silently did nothing.

## Server

- Stores groups of work for the Attention page: the items in each, what each waits on outside GitHub, your comments to the agent and its standing rules. New endpoints under `/api/attention` create, change and remove them, and the page data now includes them. The page itself starts using them in a later release.
- `/api/attention` says when a refresh can next collect.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.11.0...0.12.0
