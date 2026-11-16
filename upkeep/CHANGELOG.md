## Server

- Failures of a job that's no longer in the catalogue, such as one that's been renamed, are settled when the server starts: they leave the Failures list as cancelled, along with their heals and anything they asked of you. Queued runs of such a job are dropped, since no worker would take them.
- Nothing new is queued for a job that's no longer in the catalogue, such as a heal retrying one of its old failures.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.67.0...0.68.0
