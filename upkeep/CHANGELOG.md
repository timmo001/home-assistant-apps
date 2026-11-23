## Jobs

- New `gh` and `packages` machine jobs run `dot up gh` and `dot up packages` on the workers that list them, installing missing gh extensions and upgrading the rest, and installing the listed packages that aren't installed. Both are opt-in, so with `containers`, `system` and `clean` a headless server can run everything an interactive `dot up` does.
- The jobs GitHub events already cover now run on their schedule at a slower catch-up pace, since events start them within seconds anyway.
- branch-drift keeps each repository's branches in one run at a time, and its agent runs the repository's pre-push checks before pushing.
- branch-drift tries a branch again on the next run when it was pushed to while its agent was rebasing it.
- branch-drift flags a run only for what its branches ended up as, and the inbox only shows a rebase when it changed the branch's own commits, titled with what changed.
- A drift run scoped to one repository reads its `tooling.yml` directly rather than through code search.
- Repositories that have never had a release are listed separately, without being flagged or counted.

## Dashboard

- A run's actions sit together under its title, and back buttons line up with titles.
- The dashboard knows which worker is on the machine it's open on, so agents launch there by default, and each action says how it went.

## Internals

- Server changes roll out through the `upkeep-git` package, with a check that the server upgraded and a way to force it.
- Dependency updates: OpenCode 2, `@tanstack/lit-virtual` 3.15.5 and `@effect/tsgo` 0.73.4.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.72.0...0.73.0
