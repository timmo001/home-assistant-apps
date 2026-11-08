## Jobs

- Regression checks for bumps and dependency updates (timmo001/upkeep#90). A repository opts in with `bump.repos[repo].regression` (the commands to run) or a mise `regression` task, and the setting wins. After its checks and before the push, an update is decided by rules first: majors, minors below 1.0 and release notes that mention a breaking change are checked; lockfile-only moves and updates with empty release notes are skipped, so lock file maintenance is never checked.
  - A bump reads each release's notes once, and a dependency update group takes the most severe verdict of its updates, reading notes from the source's GitHub releases only when the update type can't settle it.
  - With regression commands, they run, and the update fails if one does. With none, the update is held unpushed and handed to an agent, Renovate's pull request stays open, and in a run with failures the held repositories count as failures with a clear line.
  - Anything the rules can't settle goes to the decision model in `heal.decisions`, asked once per release or version change. At or above `regression.threshold` (0.3 by default) it's checked, below it's skipped, and with no model or a failure it's checked. `regression.decisionsPerDay` caps the model's decisions in any 24 hours, counted on the server across workers and apart from the heal's cap.
- The deps job plans and applies Renovate's replacements (`replacementName`, `replacementVersion` and the `replacements:*` presets) on their own `renovate/<name>-replacement` branch, renaming `package.json` entries and unpinned workflow actions (timmo001/upkeep#77).
- The deps job plans fixes for the repository's open Dependabot alerts as Renovate's `vulnerabilityAlerts` do, on their own `-vulnerability` branch with no schedule or `minimumReleaseAge`. This needs the GitHub App's read access to Dependabot alerts; without it the job warns and plans no fixes (timmo001/upkeep#77).
- Bumps and dependency updates run a repository's `generate` commands and commit the generated files with the update (timmo001/upkeep#94).
- A bump waits for the release's own packages that a bumped package depends on before installing (timmo001/upkeep#92).
- A failed bump check logs the failed mise task's own lines rather than the whole output (timmo001/upkeep#91).

## Server

- New work endpoints record the decision model's regression decisions and count them since a time, for the daily cap. They're stored in a new table and pruned hourly with the GitHub events.

## Internals

- The heal's decision model setup moved to a shared module used by heals and regression checks, and running a command moved out of the bump job.
- `@timmo001/effect-gh` is updated to 0.13.0.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.40.0...0.41.0
