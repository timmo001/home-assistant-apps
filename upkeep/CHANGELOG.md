Failed runs now follow their recovery instead of staying red, the dashboard installs as an app and moves itself onto new releases, and several common causes of failed runs are fixed.

## Run states

- A failed run no longer just says Failed. It moves on as it's healed: **Heal waiting** while the daily heal limit holds it, **Healing**, **Retrying**, **With agent**, then **Fix pushed**, **Needs you** or **Parked**. Once a later run of the same job passes, it ends as **Healed** (a heal was involved) or **Recovered** (it came right by itself). **Failed** is now only for a failure nothing is healing.
- A heal run ends as what it did: Retried, Fix pushed, Nothing to fix, Needs you, Parked, or Failed when the heal itself broke, instead of Succeeded.
- Runs link both ways: a failed run lists its heals, its retry and the run that settled it, and a retry links back to what it retried.
- A failure of a job and target that already has a heal under way joins that heal, instead of starting another one.
- Runs from before this release are filled in when the server starts, so old failures that have since passed show as Healed or Recovered.
- Activity still counts every run that failed, settled or not.

## Dashboard

- Every run state has its own badge, colour and icon.
- A **Still open** button beside Filters lists only failures nothing has settled yet.
- A run's page links to its heals, its retry and the run that settled it, and a heal run's page shows its Result.
- The dashboard can be installed as an app over HTTPS, with an install banner (until you turn it down) and an Install app button in the app bar. It starts offline after the first visit. On plain HTTP and inside Home Assistant it isn't offered.
- When the server is updated while a dashboard page is open, the page reloads itself onto the new version once, and shows a Reload banner if that didn't help.

## Jobs

- A worker's notifications also tell you about new **Needs you** items on the Attention page. Work items wait for work time, and don't all arrive at once when it starts.
- Bumping consumers waits until npm actually serves the new version, and retries the install, so a release no longer fails its bumps while npm catches up.
- A workflow still running counts as pending in `ci`, not red.
- A heal no longer offers to retry a run a heal queued, so retries don't stack.
- A release tag with or without its leading `v` is the same release, so `v1.2.3` and `1.2.3` no longer queue it twice.
- Fix and change agents are told never to use Docker or root.

## Server

- `runs` takes `open=true` for failures nothing has settled.
- The server turns away a dashboard page from another version with a 426, so it can reload. The CLI and workers don't say a version and are never turned away.

## CLI

- `upkeep runs` shows the new states and each run's links, and `upkeep runs --open` lists open failures.

## Internals

- The worker puts the local bin directory on its PATH and logs the tools it resolved at start, and the machine job names a `dot` that isn't the dotfiles one, such as Graphviz's.
- Dependency updates, including Groundwork 0.45.0 and OpenTUI.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.58.3...0.59.0
