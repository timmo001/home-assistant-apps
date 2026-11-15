## Dashboard

- The runs lists have presets beside Filters: Default, Everything, Failures, Waiting on you and Running. Each one sets the State filter in one press and leaves your other filters alone.
- Still open leaves out failed commands. You watched them fail and nothing runs the same command again, so they keep their Failed state without staying open.
- Updated Groundwork to 0.46.0.

## Server

- A failed skill change now settles when a later review of the same skills in the same repository passes, whatever started it, or when a change to them lands. Before, it needed the exact same command, reason included, so most never settled.
- On upgrade, the skill-change failures that later reviews already covered are settled.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.60.2...0.60.3
