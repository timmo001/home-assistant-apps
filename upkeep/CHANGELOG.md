## Dashboard

- The runs tables, on the Jobs page and each job's page, load older runs as you scroll to the end. Skeleton rows stand in for the next page while it loads, a page of 50 at a time, until there are no older runs. Runs that drop off the latest page as new ones arrive stay in the list, so nothing goes missing between pages.
- Groundwork 0.22.0: each day's heading stays pinned under the column headings while its runs scroll past, the header and headings run the table's full width with its own scrollbar thumb drawn over the rows, links in cells no longer draw over the header, and the scroll length holds steady as rows come into view. Scrollbars inside menus, popovers and tables are thinner and fainter until hovered.

## Server

- The runs list takes a `before` run id and returns the runs queued before it, in the list's own order, so pages never skip or repeat runs queued in the same millisecond.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.50.1...0.51.0
