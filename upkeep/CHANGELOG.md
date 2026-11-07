## Server

- **Workers can read the status.** New `GET /api/work/status` gives a worker the same status as `/api/status`, so it can tell you when something new needs you (#89).

## Jobs

- **Notifications for what needs you.** A worker with `notify` in its config runs `notify.command` once for each new item that needs you, such as a heal that asked, a parked job or a skill change waiting, with `{title}` and `{url}` filled in. It reads the status once a minute. The first read after a start only records what's there, so restarts don't repeat old notifications, and nothing is sent for green runs (#89).

## CLI

- `upkeep status --bar-json` puts a wrench before the count, so the bar says what it's for.

## Agents

- The OpenCode plugin has a TUI part that shows the count of what needs you in the prompt footer, and lists each item when clicked.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.26.0...0.26.1
