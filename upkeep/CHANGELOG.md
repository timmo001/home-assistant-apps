## Server

- An OpenCode agent left waiting on a permission prompt now shows under **Needs you** on the dashboard and in `upkeep status`, with the session's title, its directory, the worker and what it wants to do. It counts towards the warning state and the notification for new items, and settles by itself once the prompt is answered. Dismissing one keeps it dismissed while that prompt waits.

## Workers

- Each worker watches its own machine's OpenCode, every session, Upkeep's or yours, for permission prompts, reading the background service from `$XDG_STATE_HOME/opencode/service.json`. A prompt is reported once it's waited a minute, so one answered straight away never shows. A machine without OpenCode running reports nothing. This reaches workers with the next `upkeep-git` package.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.43.0...0.44.0
