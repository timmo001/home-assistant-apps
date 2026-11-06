## Server

- Your pull requests no longer go under **Blocked** just because their base branch changed files they touch. With no conflict there's nothing to fix, so they now sort as **Waiting on others**, and the **base moved** signal still shows on the item. Conflicts and failing checks still block.

## Jobs

- The labels job runs the conventions CLI through mise, so it finds Bun without the shims on `PATH`.
- A repository's `install:hooks` task runs before a job commits in its clone.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.16.4...0.16.5
