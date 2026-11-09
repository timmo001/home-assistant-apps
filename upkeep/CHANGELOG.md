Release reviews move into Upkeep from the dotfiles' `dot git releases` and the Git panel: what changed since each repository's last stable release, the release it needs, and publishing it.

## Jobs

- New `unreleased` job, every 15 minutes: compares each repository tracked for it with its last stable release, from a bare clone, without a checkout. Every net change is read from Git: files, the dependencies and metadata behind `package.json`, Bun lockfile and `go.mod` changes, and the upstream changes behind `oxlint-rules`' vendored submodule. A policy (`application`, `oxlint-rules` or `system-bridge`) and the repository's own overrides give each an impact, and the highest is the suggestion. Evidence hashes match `dot git releases`, so choices made there carry over.
- New `release-publish` job, on request from the Releases page: checks the comparison and version are still the ones you confirmed, sets the version in the repository's version files, runs its commands, checks they changed nothing else, pushes the version commit and tag in one atomic push and creates the GitHub release, with your notes before GitHub's or in their place. A failed publish is never healed.
- The `command` job can open an agent to prepare a release, briefed with the comparison, through the worker's `attention.launch`.
- Each repository's release settings go in the worker's config file under `releases.repos`: branch, policy, versioning (`semver`, `calver`, `fork` or `fork-base-js`), the source-size threshold, overrides, the publish recipe and when a suggestion needs you.

## Dashboard

- New Releases page: each repository with its last release, what its changes suggest and the next version; open one for its changes worth a release, the quiet ones, its commits, impact choices for each change or the whole comparison, Compare again, Publish and Prepare in an agent. The menu counts the repositories with changes worth a release.
- The Attention page lists the repositories with unreleased changes, linking to the Releases page.

## Server

- Keeps each repository's last comparison and your impact choices. A failed or incomplete comparison keeps the last complete one, marked stale; choices stay while the evidence they were made on does.
- A suggested release at or above the repository's minimum impact counts in what needs you, so worker notifications tell you once per suggestion. It doesn't turn the status to warning.
- Protocol 5: workers need this release's `upkeep-git` to take runs.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.44.0...0.45.0
