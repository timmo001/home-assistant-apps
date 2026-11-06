## Jobs

- A new `sync` job keeps the copies apps take from groundwork current. Every hour it finds the repositories with a `sync.json` and runs groundwork's own sync over them. An app's edits to a QML copy go back into groundwork, then groundwork's changes are copied out. Each changed repository is checked, pushed to its default branch and its CI watched. A copy edited in both places fails its app, so a heal hands it to an agent. Repositories already tracked need opting into it with `upkeep repos add <repo> --job sync` alongside their other jobs. Set `UPKEEP_SYNC_DRY_RUN=true` on a worker to log what would change without changing anything.

## Internals

- Updated docs-kit, groundwork-tokens and groundwork-ui to 0.9.40.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.17.1...0.18.0
