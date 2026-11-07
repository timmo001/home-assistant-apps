## Inbox

- Move an inbox entry between Worth reading and Version bumps from its Move menu; the move holds for later versions of the same update or drift. You can also set a rule for a repository, from the same menu, `upkeep inbox rule <repo> bumps|worth|upkeep` or the `inbox_rule` tool (#59).

## Dashboard

- Tables and lists scroll smoothly. Before, every row was taken off the page and put back whenever a new one scrolled into view, which cost up to 77ms a frame and showed blank space until the rows drew in.
- A table in its own frame, such as Jobs, keeps its place when new data arrives, rather than jumping back to the top.

## Internals

- Groundwork 0.10.8, which puts Groundwork's CSS in cascade layers.
- Database migration 0031_inbox_moves.
- Update the desktop worker only after the server is on 0.34.0, since the new worker expects the inbox's placedBy.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.33.0...0.34.0
