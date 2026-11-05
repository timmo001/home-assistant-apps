## Jobs

- **Command**, a new job that does one thing on GitHub when asked, run by a worker. The first is marking a notification read. The same command still waiting isn't queued twice, and a failed one is never retried by a heal.
- **Attention** leaves out items carrying a label listed in the worker's `attention.ignoreLabels`, along with their notifications.

## Dashboard

- **Hide** on each Attention item takes it out of its section until anything about it changes. Hidden items sit in a folded Hidden section, where Show brings them back.
- **Mark read** on items with an unread notification marks it read on GitHub through a worker. The page shows it read straight away instead of after the next collection.

## Server

- `POST /api/attention/commands` queues a command, and `POST /api/attention/hide` hides or shows an item.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.10.0...0.11.0
