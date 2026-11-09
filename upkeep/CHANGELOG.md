## Jobs

- When you press **Ask me in the Inbox** on a heal that needs you, the agent is now told the run's ID. Once the work is done and nothing waits on you, it dismisses the run itself, so it stops showing as needing you.
- `deps` updates Docker images: it reads image references in Dockerfiles, Compose files and workflows, looks up tags, digests and dates from their registries, and plans updates with Renovate's `docker` versioning and `versionCompatibility`.
- `deps` only notes Renovate config that could change a repository's updates.

## Dashboard

- Updated to Groundwork 0.14.0 (`@timmo001/groundwork-tokens`, `@timmo001/groundwork-ui`).

## Docs

- Documented Docker image updates, `deps` notes, nested overrides and name templates, and how the Inbox-asked agent dismisses the run.
- Updated to `@timmo001/docs-kit` 0.14.0.

## Internals

- Updated the shared `timmo001/workflows` to 20261108.2.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.42.0...0.43.0
