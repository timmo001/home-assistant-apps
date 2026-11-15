# Home Assistant Apps Guidance

## Scope

- This repository is the Home Assistant add-on repository for my apps. Add it
  to Home Assistant once; the [README](README.md) lists the apps.
- Each app folder (`kestrel/`, `opencode/`, `opencode_manager/`, `triage/`,
  `upkeep/`) is a copy of that app's own repository. Make app changes there. A
  release copies the folder in through
  [Update app](.github/workflows/update-app.yml), which overwrites local edits.
- Only repositories listed in [`apps.yml`](apps.yml) are accepted.

## Stack

- `mise.toml` pins every tool and `mise.lock` locks them, including Node for
  Prettier and markdownlint-cli2. There is no package.json.
- Prettier formats Markdown, YAML and JSON, skipping `.mise/`, `AGENTS.md` and
  the app folders.
- `hk.pkl` runs the shared lints (markdownlint, yamllint, actionlint and
  ShellCheck) on pre-push, from
  [timmo001/workflows](https://github.com/timmo001/workflows).

## Checks

- Run `mise run check` before committing. `mise run format` writes Prettier's
  fixes.
- CI runs actionlint and yamllint in
  [`.github/workflows/lint.yml`](.github/workflows/lint.yml).
- Leave the app folders alone when linting or formatting. Their own repositories
  check them.

## Rollout

- Commit and push to `main`, the default branch, once `mise run check` passes.
- Keep Markdown within the shared markdownlint limit of 80 columns, except
  tables and blocks wrapped in `markdownlint-disable MD013` comments.
