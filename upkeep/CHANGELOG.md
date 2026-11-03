## App

- **Triage is found by itself.** With the triage app from the same app repository installed and running, Upkeep asks the Supervisor for its address on startup, so only `triage_host_token` and `triage_admin_token` need setting. `triage_url` is still there for a triage server anywhere else, and wins when it's set. The server logs the triage address it uses, or a warning when the tokens are set but no triage was found.
- The app now has `hassio_api` access, used only to read its own info and the triage app's.

## Jobs

- **New `deps` job (Dependencies), every 6 hours, read only.** It reads each repository's Renovate config at runtime, including presets (from a bundled snapshot), `packageRules` matching, grouping and automerge, turns it into Upkeep's own update groups, and logs each group and who owns it. It changes nothing yet. This is stage 1 of Upkeep's own updater (timmo001/upkeep#5).
- **`stalled-updates` no longer pushes untested updates.** A failed update in a repository with no check or build task to try it on is now left for its updater. Before, it was pushed as-is, and one such push broke a default branch's tests.

## Workers

- Workers need a build with the `deps` job before it's queued. `upkeep-git` r92 or later has it.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.9...0.1.10
