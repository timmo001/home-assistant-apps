## Server

- Failures that a later run already passed or found nothing to do for are now settled, as Recovered or Healed, with a link to the run that settled them. Before, only runs that ended after 0.59.0 settled anything, and a skipped run didn't count until 0.59.2.
- Retries queued before 0.59.1 lost the machine their run was for, so a retry that passed didn't settle the failure it retried. Those retries get the failed run's command back when they ran on the same machine, and settle it.
- A failure stuck on Retrying after its retry failed goes back to Failed.

## Internals

- Upkeep changes skip the Plannotator review step.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.59.2...0.59.3
