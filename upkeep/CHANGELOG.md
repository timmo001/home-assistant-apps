## Dashboard

- Tables in their own frame, such as the Jobs table, scroll properly. Before, a table drew its rows again on every scroll and lost its place, so it wouldn't scroll at all, and the page didn't scroll either while the pointer was over it.
- Scrolling past the end of a table, list or code block carries on and scrolls the page, as does scrolling over one with nothing more to show.
- Scrolling a long table or list is lighter, as rows already in view are kept rather than drawn again.

## Internals

- Groundwork 0.10.6.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.32.0...0.33.0
