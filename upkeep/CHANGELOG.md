The server no longer logs every successful request, and workers find `dot` and OpenCode on the PATH they give their jobs.

## Server

- Successful responses are left out of the server log. Workers and dashboards poll the API all day, and logging every answer pushed everything else out of a host's journal. Failed requests and 4xx and 5xx responses are still logged.

## Workers

- Workers look up `dot` and the OpenCode command on the PATH they give their child processes, which includes `~/.local/bin`, rather than the PATH the worker started with. Startup no longer reports `dot` as Graphviz on hosts where `~/.local/bin` comes later, and the missing OpenCode warning no longer shows when it's installed there.

## Internals

- Updated wrangler to 4.166.0, oxlint-tsgolint to 7.0.2008 and jdx/mise-action to v5.3.0.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.71.0...0.71.1
