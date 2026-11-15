A run that finds nothing to do now settles a failure, the same as one that succeeds.

## Server

- A failed run is settled by a later run of the same job that found nothing to do, such as an `up-tools` or `up-skills` run with nothing to update, not only by one that succeeded. Before, a machine job's failure could stay open for days after it was fixed, and a retry that found nothing to do moved its failure back to Failed.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.59.1...0.59.2
