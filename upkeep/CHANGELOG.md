## Jobs

- A finished package publish in `arch-repo` now queues `up-first-party` on every worker. 0.50.0 matched the workflow's name, `Publish package`, but GitHub's event carries the run's name, such as `Publish system-bridge-git`, so the rule never fired. It now matches any run that starts with `Publish `, and no other workflow there does.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.50.0...0.50.1
