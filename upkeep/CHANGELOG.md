## Dashboard

- **Start agent** asks where to start the agent: the repositories the item or group is on are suggested first, Upkeep is always offered for moving or sorting issues, and every other tracked repository follows. It starts on the worker you used last, with the others offered in the same menu.
- An item or group shows how its agent start is going: asking, waiting for the worker, starting, then started or why it couldn't, with a link to the run. The button spins meanwhile, so it can't be started twice.
- The Jobs page lists the new Command lane.

## Jobs

- The command job has a lane of its own, which workers check every 3 seconds, so starting an agent or marking a notification read no longer waits up to 30 seconds or behind the attention context agent.
- Starting an agent reads GitHub for the brief and finds or clones the checkout at the same time, and logs each step. Started outside the item's repository, the brief tells the agent to work on it through `gh` instead of checking it out.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.16.5...0.17.0
