Upkeep now knows each repository by its real name.

## Jobs

- `watch` reads each tracked repository's title from its README's first heading, such as "System Bridge", and keeps it on the server, so the dashboard can show titles instead of slugs.

## Server

- Tracked repositories have a `title`, returned by `GET /api/repos` and set by workers through `POST /api/work/repos/titles`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.6.2...0.6.3
