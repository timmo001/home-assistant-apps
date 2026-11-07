## Server

- **A missed schedule catches up on start.** A job whose scheduled time passed while the server was down, such as during an upgrade, now runs once as the server starts, rather than waiting for its next time. The server logs "Catching up …" for each one. Only jobs with an earlier scheduled run are caught up, so a fresh install doesn't start everything at once.

## Dashboard

- **Your own commits start read.** A new inbox entry of your own commits starts read, and stays read as more of yours join it. It's still in the inbox as history, but isn't counted as new or summed up as unread. Anyone else's change joining an entry still marks it unread.

## Jobs

- **gh failures say what happened.** A gh command that printed nothing now reads as "gh: exited with 1, printing nothing", or "gh: was stopped by signal 15 (exit 143), printing nothing", and a timeout as "gh: timed out after 2m", in run errors, heals and logs. Any other error with an empty message shows its name instead of a blank.
- **Heals ride out a GitHub outage.** A heal's agent that can't start because gh printed nothing now waits and starts again after a minute, then two, then four, as it already did for rate limits. If it still can't and the run failed on gh too, the job is queued again instead of left for you.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.29.0...0.30.0
