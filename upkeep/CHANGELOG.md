A retry now stays on the machine its failed run was for, so its success settles that failure.

## Server

- Retrying a failed machine job, such as `up-tools`, by hand or from a heal, runs it again on the same worker. Before, the retry could go to any worker, and when it passed it didn't settle the run it retried, which stayed Retrying.

## CLI

- The MCP `runs` tool takes `open`, to list only the failures nothing has settled yet.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.59.0...0.59.1
