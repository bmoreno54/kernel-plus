# Cold Computation — Trunk Protocol

**Status:** Candidate (promoted from hearth session 2026-04-24)
**Tags:** #kernel+ #trunk #protocol

## Principle

The ecology is cold by default. No scheduled tasks, no warm automation, no polling, no continuous processes. All state is derivable at the moment of human engagement using math and coordinate systems. The human arriving IS the trigger. Everything computable is computed at run-time from current state, not maintained by warm processes.

## Distinction: Cold vs Warm vs Extended Catalysis

- **Warm automation** (anti-pattern): cron jobs, polling loops, scheduled tasks, watchers that run without human presence. These are leaky tech debt — they cost energy, create staleness assumptions, and diffuse the human's catalytic role.
- **Cold computation** (default): derive everything at runtime from stored state + math. The omnibus is an append-only log; state is computed from it at query time. Signals accumulate stigmergically; the next session reads the surface.
- **Extended catalysis** (valid): the human says "keep going" — sustained injection. The human IS the trigger, extended in time. This is not warm automation; it's a long catalytic event.

## Application

When encountering any of these patterns, identify them as cold-computation candidates:

- Scheduled tasks (cron, Task Scheduler, systemd timers)
- Background polling (check for updates, watch for changes)
- Warm caches (pre-computed state maintained between sessions)
- Continuous processes (daemons, always-on services)

Replace with:
- Append-only logs + runtime derivation (event sourcing)
- On-demand computation triggered by human engagement
- Mathematical convergence without coordination (CRDTs)
- Stigmergic signals read at encounter time

## The Minimum Warm Surface

Some systems require a warm listener to catch the human's first gesture (e.g., a hotkey daemon on Windows). This is the irreducible warm surface — everything after the first gesture should be cold.

## Corroboration

Seven independent fields discovered this:
- Event Sourcing / Datomic (Hickey, 2012)
- Lazy Evaluation (Haskell, 1990)
- CRDTs (Shapiro et al., 2011)
- Stigmergy (Grassé 1959, Heylighen 2016)
- Enactivism (Varela/Brooks 1991)
- Serverless / Lambda (AWS 2014)
- Calm Technology (Weiser 1991)

Full research at `hearth/notes/fade_cold_computation_corroboration_2026-04-23.md`.
