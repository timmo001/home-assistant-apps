## Dashboard

- The runs table's filters now live in the page's address, such as `?state=failed,needs-you&job=deps&day=2026-11-15`, so a link or bookmark keeps them and the back button brings them back. The table's own view state, such as its sort, is still kept as before.
- Every filter offers each value it can take, not only those the runs on screen have: every run state, every job and every trigger, with a count of 0 for those with no runs.
- Still open is now in the Filters sheet as a switch, counted with the other filters and shown as a chip that takes it off, rather than a button of its own.

## Jobs

- A failed run's error says what went wrong instead of a stack trace into the bundled binary. Each expected error is one entry with its tag and message, and what caused it, such as the executable a spawn couldn't find. A defect still shows its full stack.
- A run that failed in some of its repositories (bump, deps, drift, CI, sync and stalled updates) names why each one failed in its error, as the job logged it, rather than only listing them. A deps run that failed on a check now shows the check's own output.
- A machine job's stage that exits without a result names the last line `dot` printed, instead of only its exit code.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.60.0...0.60.1
