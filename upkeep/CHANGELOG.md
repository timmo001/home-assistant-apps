Upkeep's dashboard now opens on an inbox: what changed in your repositories since you last looked, and what really needs you.

## Dashboard

- The home page is an inbox. A few sentences at the top sum up what's new: first-party releases and where they went, your own commits, updates that needed a code change, how many routine updates there were, and whether anything needs you.
- **Needs you** only holds what won't settle without you: a parked job, or a heal that asked for you or left a fix unfinished. A job parked again and again shows once, with a count, the button to unpark it and Dismiss, and leaves once it's settled.
- **What changed** shows one entry per change, by day. A release rolled out by bump, a tool moved by drift or the same Renovate update across repositories is one entry that opens to each repository and commit. Your own commits are grouped by repository and day.
- Routine updates, ones that only move versions, lockfiles, pins or tool versions, fold into one line that opens to the list.
- Entries stay unread until you open them or mark everything read, and come back when something new joins them.
- Jobs and the latest runs moved to a Jobs page, linked from the new menu in the header.

## Jobs

- New `watch` job, every 15 minutes: reads the last 48 hours of commits on each tracked repository's default branch and adds the ones the inbox doesn't have, so commits made outside Upkeep's own runs show too. It reads every tracked repository, whatever it's opted into.

## Server

- The inbox is kept in the server's database and served at `GET /api/inbox`, with `POST /api/inbox/read` and `POST /api/inbox/{id}/dismiss`. Bumps, drift moves, stalled updates and heal fixes join the inbox as they're pushed, and a heal's fix joins the release it was fixing.
- On first start the inbox fills from the commits runs pushed in the last 48 hours.
- Read and dismissed entries are deleted 30 days after they last changed.

## Internals

- Heals message the Inbox once per repository again: each heal's message has its own idempotency key, so the messages for several parks from one failed run all arrive.
- Git commands in bump, drift and stalled updates retry GitHub's transient errors with backoff.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.5.0...0.6.0
