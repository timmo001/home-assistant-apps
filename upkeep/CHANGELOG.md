## Inbox

- groundwork's copies the Sync job pushes to the apps are version bumps now, grouped one entry per sync across apps, rather than one "worth reading" entry per app. The edits it carries back from the apps to groundwork are yours and start read. The existing entries are moved the same way when the server starts.

## Internals

- The dashboard builds into a directory of its own for each bundle, so the tests and the binary's build no longer race over the same `dist` in CI.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.58.0...0.58.1
