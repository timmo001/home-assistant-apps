## Dashboard

- Group cards on Attention fold like the Backlog, Parked and Hidden sections around them: the whole heading opens and closes them, with the same round chevron on the right, and Start agent, Focus and More stay beside the heading. Each group's open or closed state is still remembered per browser.
- Since you last looked is one line: how many changes since when, links to the first few, and the full list behind Details.

## Jobs

- `deps` reads git submodules when the Renovate config turns on the `git-submodules` manager, following each one's `.gitmodules` branch or its remote's default branch.
- `deps` fetches a config's `customDatasources` in their format (`json`, `plain`, `yaml` or `toml`) and runs their JSONata transforms, as Renovate does.
- Setting `"enabled": false` in a repository's Renovate config hands it to Upkeep entirely: Upkeep keeps reading the rest of the config and owns every group, including the ones Renovate would have automerged.

## Internals

- The dashboard is on groundwork 0.9.37.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.16.0...0.16.1
