## Jobs

- `deps` applies the update groups Upkeep owns in the repositories listed in `deps.apply`, and the catalogue now says so rather than "Changes nothing yet".
- `deps` reads files from a checkout instead of the contents API, and checkouts init submodules when a repository has them.
- `deps` applies prerelease updates, custom regex matches and mise `[tools."x"]` tables. An update it can't apply is left to the updater with a warning instead of failing the run.
- `deps` reads jsonata custom managers (workflow input defaults, OpenCode reference tags) and applies their updates where the value appears once in the file.
- `deps` reads `pipx:` and `pypi:` mise tools from PyPI, and knows aube's and golangci-lint's repositories.
- `deps` keeps GitHub responses between runs and asks for them again with their ETags, so releases, tags and commits that haven't changed cost no rate limit.
- Runs wait out a spent GitHub rate limit instead of failing.
- `bump` searches for a package's consumers by its bare name.

## Dashboard

- The agent-written inbox summary sits in an expansion that stays closed until it's opened.

## Internals

- Updated @timmo001/effect-gh to 0.11.0, @timmo001/effect-triage to 0.21.0, @timmo001/oxlint-rules to 0.6.4, @timmo001/docs-kit to 0.9.36 and minimatch to 11.0.1, and added jsonata 2.2.2.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.7.0...0.7.1
