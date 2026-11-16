## Jobs

- `deps` no longer runs as one long job. A scheduled or manual run for every repository is queued as a batch: one short run per repository tracked for deps. Each takes a few minutes, a run that's interrupted, fails or is retried only covers its own repository, and a waiting event run for a repository joins the batch rather than running twice (timmo001/upkeep#103).
- `deps` watches CI once per repository, on its last push, instead of after every group. Each group is still checked and pushed on its own, and Renovate's pull requests are closed once that CI passes. A CI failure names every group in the batch. Watching CI took most of a long run's time.
- A regression decision is reused for a week: the same model's answer on the same update, from any run on any worker, judged against the current threshold. Repositories moving the same dependency no longer each ask the model and use up its daily limit.
- `deps` keeps the GitHub responses other runs read, dropping only those no run has read for a week, so one run per repository doesn't throw away the others' free 304 reads.

## Server

- The lane takes a batch's runs after its other runs, so `bump`, `sync` and `drift` no longer wait behind `deps`.
- A batch's failures wait for the whole batch to end, then share one heal over every repository that failed, reading each one's error and log, as one run of the whole job did. Its retry runs each of those repositories again. This also happens when the last run of the batch is lost or cancelled.
- New `/api/work/regression-decisions/latest` endpoint, for a worker to find an earlier decision on an update.

## Internals

- The CLI and worker keep the original error as the cause when narrowing one.
- Updated `@timmo001/oxlint-rules` to 0.7.1.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.63.1...0.64.0
