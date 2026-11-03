## Jobs

- **The `renovate` job is now `stalled-updates`.** It isn't tied to Renovate any more: it takes over Dependabot pull requests whose checks failed as well as Renovate ones, finding them by author rather than by branch prefix, so a repository's `branchPrefix` or other updater config makes no difference. Onboarding pull requests are spotted by their title or a `/configure` branch. Its clones move to `upkeep/stalled-updates` in the XDG cache, and the dry-run setting is now `UPKEEP_STALLED_UPDATES_DRY_RUN`.
- **Pull requests that conflict with the default branch are left for their updater to rebase**, rather than failing the run. GitHub's mergeable flag is checked first, and a conflict found while squashing is left the same way.
- **A dry run no longer fails.** It logs the repositories it would have failed in, so it queues no heals whose agents would push for real.

## Server

- **Heals are limited per target, not per job.** `UPKEEP_HEALS_PER_DAY` now applies to each repository a job fails in, so one repository failing all day no longer parks the job for the rest; that repository just gets no more heals until tomorrow. A job failing in itself is still parked once it passes the limit.

## Internals

- Release, dev server and workspace package guidance moved out of AGENTS.md into the repository's `upkeep-release`, `upkeep-dev-servers` and `upkeep-packages` skills.
- New app releases are installed through the ha-bridge tools.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.4...0.1.5
