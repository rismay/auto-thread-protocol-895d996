# Auto Thread Protocol (Provisioned)

This is a **provisioned DocC bundle** meant to be shareable and deployable via `swift-docc-deploy`.

## Purpose

Define the operator-thread protocol for:

- `thread handoff [profile]` (default driver: `clia`)
- `thread handoff disable|off` (turn auto mode off)
- `thread freeze` / `thread unfreeze`
- thread priority (P0–P3) + runnable selection
- canonical on-disk thread records sufficient to:
  - prioritize work when no incident is active
  - generate idempotent DocC mirrors of thread history

## Quick command contract

- Enable auto mode:
  - `thread handoff`
  - `thread handoff clia`
  - `thread handoff codex`
- Disable auto mode:
  - `thread handoff disable` (alias: `off`)
- Hard pause:
  - `thread freeze`
  - `thread unfreeze`

Reserved keywords (cannot be profile names):
- `disable|off|on|freeze|unfreeze|status|help`

## Canonical storage + mirrors

- Canonical data is **not** the DocC mirror.
- The mirror is generated from canonical thread events/state.
- Default visibility: private → `threads/private/...`

## Source request

- In-repo design request (internal): `.clia/docc/requests.docc/clia-agent-cli-thread-command.md`
