## Jobs

- `deps` stops listing a dependency's releases and tags once it reaches the version in use, so a repository's updates take a page or two of reads rather than its whole history.
- `ci` keeps each repository's details and workflow list between runs and asks for them again conditionally, so a repository that hasn't changed costs no rate limit.
- `watch` checks each default branch's newest commit conditionally and only lists commits on branches that moved since its last run. READMEs for repository titles are read conditionally too. A run that fails keeps nothing, so the next one reads everything again.

## Internals

- The conditional-GET cache from 0.7.1 is now shared by `deps`, `ci` and `watch`, each keeping its responses in `$XDG_CACHE_HOME/upkeep/<job>/github.json`.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.7.1...0.7.2
