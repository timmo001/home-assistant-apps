## Jobs

- A worker can rest in quiet hours set in its settings (`quietHours` with `start` and `end`, such as 00:00 to 07:00). It takes no new scheduled runs then, its status reads "Quiet hours", and notifications wait until they end. Commands from the dashboard still run, and the server keeps counting it as live.
- A heal handed off to you now leads with the work it did, shows what its repository was handed and logs it, and its reason names the releases involved.

## Dashboard

- A heal that left something for you has **Ask me in the Inbox** beside its session. It resumes the session in the background on the worker that ran it, telling the agent to load the `plannotator` skill and ask you what it needs in the Plannotator Inbox (timmo001/upkeep#93).

## Internals

- The worker protocol is now 4, for the new `ask-inbox` command. Workers on an older `upkeep-git` are given no runs until they update.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.39.0...0.40.0
