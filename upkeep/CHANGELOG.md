## Dashboard

- Pages stay quick however much they hold. Every folding panel draws its contents the first time it opens, behind a skeleton, so the page opens at once and a closed panel costs nothing.
- The inbox and each repository's page list entries under days that fold, and only the entries on screen are drawn. Which days you fold is kept in this browser, per page.
- Lists inside panels are tables you can sort and search: an entry's changes, Attention's What moved, Gone and Latest releases, a skill's commits and a run's commits. Each scrolls inside its own frame.
- A skill's commits show properly again, rather than spread over several lines.
- Agent summaries, on the inbox and on a run, and what an agent said on a skill change, read as markdown. A skill change's diff is shown with its added and removed lines tinted.
- A run's log scrolls inside its own frame and only draws the lines on screen, so a long log no longer slows the page.
- Which Attention panels are open is kept per panel, in this browser, and so is whether Since you last looked shows its full list. Groups you'd folded before carry over.
- Tables and panels keep their state with Groundwork's shared storage.
- A page no longer redraws when a refresh brings back the same data, so open panels and scroll positions stay put while it polls.
- Jobs nothing starts by itself, such as Summary, show On request instead of an empty schedule, and no longer offer Pause, since pausing only stops scheduled and release runs. One already paused can still be resumed. (#60)

## Jobs

- The deps job does Renovate's lock file maintenance. (#77)
- A worker retries reporting a run's end for about a minute when the server restarts mid-report, so the run doesn't stay running until it's lost.

## Internals

- Groundwork 0.10.5.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.30.0...0.31.0
