A fix for the inbox's first hour: it showed routine updates as worth reading.

## Jobs

- `watch` folds a bot's commit away as routine unless it touches source code, such as Renovate's updates and releases mirrored to another repository. A submodule moved to another commit, any `.lock` or `-lock.yaml` file and mise's `config.toml` count as routine too.

## Server

- The inbox starts again once, so the commits it already had are read again with the new rules: the server fills it from the last 48 hours of run commits, and the next `watch` run adds the rest.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.0...0.6.1
