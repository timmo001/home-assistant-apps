## Jobs

- **Dependency updates in more languages:** `deps` now reads and applies `go.mod` requirements and the Go `toolchain` (running `go mod tidy` after an edit), Gradle `"group:artifact:version"` dependencies and `id(...) version` plugins, and exact `==` pins in requirements files, compared as PEP 440 versions. Releases come from the Go module proxy, Maven Central, Google's Maven repository and the Gradle plugin portal, with the newest few dated so `minimumReleaseAge` can pass them.
- **Node.js and Python versions:** custom managers can name the `node-version` and `python-version` datasources, which read releases from nodejs.org and python.org.
- **Repositories with pull requests turned off:** `deps` no longer fails after landing an update when looking up the updater's pull request returns 404; there's simply none to close.
- **Bump consumers:** found from their `package.json` files as well as code search.
- **Skill changes:** pushing a skill change retries when `main` keeps moving.

## Server

- **Co-author credit:** with a GitHub App set up, the server looks up the App's bot and hands it to workers with the token. Commits that automated jobs make (deps, bump, sync, drift, stalled updates and skill consumers) stay yours and signed, with the bot credited as `Co-authored-by`. Work that waits for your approval, such as skill changes, is credited to you alone.

## Worker

- **Upgrades finish runs first:** on a package upgrade the worker is sent `SIGHUP`, takes no new runs, finishes the ones it has, and exits with code 75 for systemd to restart it, so a run is no longer cut off and queued again.

## Internals

- Updated `@timmo001/groundwork-ui` to 0.23.0.
- Renovate is off here, now that Upkeep applies its own updates.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.52.0...0.53.0
