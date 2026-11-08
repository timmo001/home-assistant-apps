## Jobs

- A run handed off to an agent, such as a `drift-review`, now gets a heal for each of its repositories instead of one heal over them all, so each repository is reviewed in its own agent session.
- Drift reviews are told to keep existing behaviour working while they add what a tool supports.

## Worker

- A worker runs up to `heal.sessions` heals at once, 3 by default, so the heals of a drift review are worked on side by side. Two heals never work on the same repository's checkout at the same time: one waits for the other.

**Full Changelog**: https://github.com/timmo001/upkeep/compare/0.38.0...0.39.0
