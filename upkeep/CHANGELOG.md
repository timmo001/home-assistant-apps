## Jobs

- A run that finds work only an agent can do, with nothing failing, now ends `handed-off` instead of `failed`. `drift-review` always ends this way when it lists repositories to review, and `drift` does when the only thing left is a release to review. Its heal goes straight to an agent, with a prompt that says it was handed work rather than asked to fix a failure, and it raises no triage issue. A run where something also failed still fails, and its heal takes the reviews with it.
- `deps` still treats a drift review after its updates as part of the group's heal, as before.

## Dashboard

- Handed-off runs show a "Handed off" badge with a robot icon.
- Groundwork is updated to 0.12.1, with its elements defined through its `define/` entries.

## Server

- Handed-off runs settle earlier heals as a successful run would, are counted on their own in the activity summary, and are pruned like other finished runs.
- The worker protocol is now 3, so workers need updating alongside this release.
- Bump consumers are searched for with the machine's login.

## Worker

- The worker status warns when the OpenCode command isn't on its PATH, so agent heals can't start.

## Internals

- Shared skills updated.
- The OpenCode plugin's TUI part is built to plain JavaScript.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.37.0...0.38.0
