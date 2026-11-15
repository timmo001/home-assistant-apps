## Server

- Running a run again is refused with `ReleaseRequired` when its job runs on releases (Bump) and the run had no release, instead of queueing a run that fails at once with `NoRelease`.

## Jobs

- A heal that decides to retry such a run leaves it for you instead, saying it had no release, rather than queueing another run that can only fail.

## Dashboard

- A run of a release job with no release no longer shows a Run again button.

## Internals

- Ask before `gh` deletes in Claude Code.
- Update the shared skills.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.60.4...0.60.5
