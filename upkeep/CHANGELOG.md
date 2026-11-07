## Dashboard

- The app bar's theme picker offers every Groundwork theme: Glazing, still the default, then Base, Survey, Slate, Bridge and Snag, then Catppuccin, Tokyo Night and GitHub. Every theme is set in Mona Sans and Geist Mono. (timmo001/upkeep#21)
- When a worker runs on a machine with Omarchy, the picker also offers the desktop's theme under Desktop, as "Omarchy (theme name)". While it's picked, the dashboard follows each theme switch on the desktop. It's never the default. (timmo001/upkeep#22)
- Icons are now Phosphor instead of Material Design Icons. Most buttons, menus, tabs, filters and options show one beside their text: the Focus menu and its choices, the Work, Personal and All scopes, the inbox kinds, Save, Resume, Ask, Start again, Sign in and the rest. (timmo001/upkeep#21)

## Server

- The server keeps the latest Omarchy theme a worker sends and serves it at `GET /api/theme`. A new `theme` topic in `/api/status/changes` tells the dashboard when it changes.

## Workers

- A worker on an Omarchy machine sends the desktop's theme to `PUT /api/work/theme` when it starts and each time Omarchy switches it. If a send fails, it tries again every 30 seconds. A worker without Omarchy sends nothing. This needs the `upkeep-git` package built from this release or later.

## Docs

- The docs site's header has the same theme picker, also in Mona Sans. Running gains a Theme section.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.31.0...0.32.0
