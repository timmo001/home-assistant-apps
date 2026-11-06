## Jobs

- New `skill-consumers` job, hourly: syncs the shared skills into the repositories listed in the skills repository's `consumers.yml`, through the `skill-maintenance` it builds from a fresh clone of the skills repository. It replaces the `skill-consumers` timer that ran on each machine.
- New `skill-updates` job, hourly: runs `skill-maintenance updates-agent device` with the config named in a worker's `skills.updatesAgent` setting, so an agent works through the latest completed skill updates workflow run. A run already processed or deferred ends as skipped, and a worker without the setting skips it. It replaces the `skill-updates-agent` timer.

## Docs

- A Skills section in Running covers both jobs and the new worker setting.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.18.1...0.19.0
