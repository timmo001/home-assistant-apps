## Dashboard

- The Jobs page shows how a job's latest batch is getting on under its last run, such as "Batch 10:21: 33 of 40 done, 1 didn't pass". `deps` runs as a batch of runs, one per repository, since 0.64.0 (timmo001/upkeep#103).
- A job's page has a Latest batch note: when it was queued, how many of its runs are done, running, waiting or didn't pass, and when the last one ended.
- On the Runs page, each run that's one of a batch says "in a batch" under its repository, linking to its job's page.

## Server

- The jobs list sends each job that fans out with its latest batch's progress, and says it fans out.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.64.0...0.65.0
