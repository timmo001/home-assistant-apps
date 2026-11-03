## Jobs

- A `bump` of a release that nothing uses now ends `skipped` instead of `succeeded`, with a log line saying there's nothing to bump. Before, every release of every repository left a successful bump run behind, even for repositories with no consumers, such as Upkeep's own releases.
- Workers report a run that found nothing to do as `skipped`, a new run state alongside `succeeded`, `failed` and `cancelled`. Skipped runs are pruned like any other finished run.

## Dashboard

- The header shows the server's version next to the Upkeep name, so you can see which release is installed without opening Home Assistant.
- Release links open in a new tab and carry an external link icon, with screen reader text saying they open in a new tab.
- The list of every job's runs leaves out skipped runs, so it only shows runs that did something. A job's own page still lists them, with a grey "skipped" badge.

## Server

- `GET /api/version` returns the server's version. It needs no token.

## CLI

- `upkeep --version` and the MCP server report the real version: the release for the Home Assistant app, the package version (such as `0.0.0.r87.gabc1234`) for `upkeep-git`, or `dev` from source. Before, both always said `0.0.0`.

## Internals

- Builds bake the version in through `UPKEEP_BUILD_VERSION`: the Release workflow passes the tag to the container build, and the Arch package passes its `pkgver`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.1.8...0.1.9
