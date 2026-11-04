## Server

- A run cut off by a worker stopping mid-run, such as a restart after an `upkeep-git` upgrade, goes back to the front of the queue instead of failing. So does a run whose worker goes quiet for 10 minutes. This happens once per run: the second time it fails as lost and heals as before, so a run that brings its worker down can't loop (#34).

## Internals

- The worker's finish report says when a run was interrupted, and the store keeps how often each run has been requeued.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.2.0...0.2.1
