## Server

- Retrying a run of a job that's no longer in the catalogue, such as one that's been renamed, is refused. Before, the retry was queued for a job no worker runs, so it sat in the queue for good and its failure stayed at retrying.
- Dropping a queued retry puts the failure it was retrying back to failed, rather than leaving it at retrying with a link to a run that's gone.

## Jobs

- Dependencies plans its updates without checking out each repository's submodules.

## Internals

- Updated docs-kit and the groundwork packages to 0.50.0.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.66.0...0.67.0
