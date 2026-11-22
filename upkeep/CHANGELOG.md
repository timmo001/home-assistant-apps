## Jobs

- New `branch-drift` job keeps a repository's long-lived branches in step with the branch each one follows. A branch opts in with a `.dot-branch.yml` at its root (`mode: rebase`, its `parent`, and paths to `ignore`). It runs daily at 05:00 and on a push to any branch of a repository tracked for it. A branch behind its parent goes to an agent (the worker's new `branches.agent` setting, or else the first of `heal.agents`) in a worktree of its own, which rebases it following the branch's `AGENTS.md` and runs its checks. The worker then checks the result and pushes it with `--force-with-lease`, so a branch pushed meanwhile is never overwritten. Parents go first, and a branch waits while its parent isn't in step. One the agent couldn't finish marks the run as needing you and keeps its worktree and session to resume. See [Branch drift](https://upkeep.timmo.dev/running#branch-drift).
- `skill-consumers` turns off the repositories' own hk pre-push lint when it pushes the vendored skill copies, so a repository that keeps MD013 on no longer fails the push over the skills' long Markdown lines.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.71.1...0.72.0
