## Server

- Agent reviews from a run that handed work off now leave the Failures list once they're done. A heal that pushed a fix or found nothing to fix settles itself, as does one asking you once you've dismissed it. One that broke or is still asking is settled by a later heal of the same repository, where a drift review covers drift.
- A failure retried by a run that handed off is settled once every heal of that handoff is done.
- A retry that doesn't pass now sends back every failure it was retrying, not only the first, so none is left stuck at retrying.
- A release job's run with no release, which could happen before that was refused, is cancelled along with its heals, since it never could have run.

## Dashboard

- The Failures and default runs lists leave out commands that failed, as Still open already did. They were seen as they happened and are never healed.
- A heal that settled itself no longer links to itself as what settled it.

## Jobs

- A run that couldn't reach a server, such as Upkeep's while it restarts for an upgrade, is queued again once, as a run the worker stopped is, rather than failing a heal that nothing then heals.
- Dependencies shares its lookups across a worker's runs, and each run reads only its own repositories.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.65.0...0.66.0
