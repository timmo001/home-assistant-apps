## Dashboard

- The runs tables, on the Jobs page and each job's page, can be filtered by state, job, trigger, repository and worker. The search and filters sit together in a **Search and filters** section over the table that folds away, with what's on shown under its heading while it's shut and a **Clear** button to take it all off. What's set is kept in this browser with the table's sort and folded days, and whether the section is open is kept too.
- Skipped runs, still left out of every job's runs by default, can now be shown there by ticking them under State.

## Worker

- The jobs that change repositories (`bump`, `deps`, `stalled-updates`, `ci`, `drift`, `sync` and the skill jobs) and the agents a heal, change or skill change starts now work in Git worktrees rather than clones of their own. A worktree comes from your checkout of the repository, at the `path` your `names` list gives it, or else from one bare clone shared in `upkeep/repos` in the XDG cache directory, and lives beside your own worktrees in Herdr's worktree folder, detached at the default branch so your checkout's branch and changes are never touched. Heals of the same repository no longer wait for each other. A run's worktrees go when it ends; an agent's are kept while it may still need you. The per-job clone folders under the cache are no longer used and can be removed.
- An agent opened from the Attention, Releases or Skills page, and a session resumed or handed off, is named as your `names` list names the repository, and one from the Attention or Releases page starts in that list's `path` when it gives one. An agent you open never works in a scratch clone in the cache: a repository with no checkout yet is cloned where your checkouts are.
- **Release in an agent** asks you once, with the findings, version and full release notes, and that answer covers preparing, validating, committing, pushing, tagging and publishing.

## Internals

- Updated groundwork to 0.19.1, `@timmo001/effect-triage` to 0.22.0 and `@timmo001/oxlint-rules` to 0.6.5, and the shared docs-kit skill.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.46.2...0.47.0
