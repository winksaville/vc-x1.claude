---
name: Add doc comments on every fn/method
description: Every function (and method) in new vc-x1 source files must have a doc comment explaining what it does. Matches existing project style.
type: feedback
originSessionId: dd6d8dec-5fd8-4f01-b77e-691afb50e95d
---
Every `fn` / method in new vc-x1 source should carry a `///` doc comment
(even private helpers). CLAUDE.md's default "write no comments" is
*overridden* for this project — the existing modules (`common.rs`,
`symlink.rs`, `finalize.rs`, etc.) already have doc comments on
essentially every function, including private helpers and small
wrappers.

**Why:** Wink explicitly asked for this when reviewing a new module
draft. Matches the house style — public API and internal helpers get
the same treatment, so readers don't have to infer intent from names
alone.

**How to apply:** Whenever writing or editing a function in `src/*.rs`,
include a `///` doc comment. Keep it short — one line for simple
wrappers, a short paragraph for orchestration functions explaining the
flow / why it's structured that way. Struct fields don't need comments
unless their meaning isn't obvious from the name.
