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

## Situated Derivation

Cold computation composes with occlusion rendering and the fountain principle into a single commitment: **situated derivation**. The ecology does not maintain a representation of itself. It renders a picture from wherever the human is standing, at the moment they arrive, through the medium of their engagement.

- Cold computation governs **state**: derive at runtime, don't maintain warm copies.
- Occlusion rendering governs **perception**: render from topology at encounter time, don't maintain a warm map.
- The fountain principle governs **production**: let products emerge from substrate at use time, don't maintain warm products.

These are the same mechanism across three registers. What cold computation does to state, occlusion does to perception, and fountain does to production. Promoting any one without the others is incomplete: cold computation alone is a performance optimization; occlusion alone is a UX pattern; fountain alone is a platitude. Together they constitute the ecology's rendering paradigm.

## Stigmergic Statefulness — The Formal Articulation

Cold computation is stateless per invocation but stateful across
invocations. The substrate is the hidden channel. The general form:

given a computation C that is stateless per invocation, a
requirement R for continuity across invocations, and a persistent
substrate S accessible to C — then C will develop read-modify-write
cycles on S, and S will accumulate structure over time. the system
(C + S) exhibits statefulness despite C being individually stateless.

the substrate does not merely store data. it accumulates structure.
reports, graphs, FADEs, signals — these are not flat records but
living knowledge artifacts. the structure that accretes in the
substrate becomes the system's primary knowledge asset. the
computation is ephemeral; the substrate endures.

this pattern is architectural necessity, not design preference.
any system that must be stateless at its invocation boundary but
must exhibit continuity will develop stigmergic persistence. the
constraint pair (stateless invocation + continuity requirement)
admits no other solution.

independent academic validation: arXiv:2602.08563 ("Stateless
Yet Not Forgetful") formalizes the same mechanism as "implicit
memory as hidden channel." the ecology's name is more operational;
the academic name is more analytical. both describe the same
structural necessity.

## The Clearing Protocol — Procedural Face of Cold Compute

Stigmergic statefulness is the mechanism. The clearing protocol is
the procedure it produces when facing accumulation surfaces.

Any agent that is stateless per invocation but must process material
that accumulates between invocations will develop a five-phase
clearing protocol:

1. **Pull** — gather what has accumulated since last clearing
2. **Triage** — separate by action-type (not by content-type)
3. **Route** — deposit extracted signal into appropriate receiving systems
4. **Clear** — return the accumulation surface to empty
5. **Learn** — update the triage model from what was encountered

This protocol is constraint-forced by a triple:

- **Finite attention** — the agent cannot process everything continuously
- **Unbounded accumulation** — material arrives whether or not the agent processes it
- **Heterogeneous content** — not all accumulated material has the same action-type

The constraint triple admits no other viable architecture. Continuous
monitoring fails at scale. Batch processing without triage fails at
heterogeneity. The five phases are the minimal complete response.

The clearing protocol composes with cold compute at every joint:
clearing runs as stateless invocation (cold), and the Learn phase
deposits its results stigmergically (substrate enrichment) for the
next invocation to discover. It composes with property inclusion
(thermal rendering): triage IS entity-level attribute-set gating —
which accumulated items earn attention. It composes with the
three-layer rendering stack: pull is data preparation, triage is
property inclusion, route/clear is rendering.

Five independent implementations discovered this protocol without
shared code or mutual reference: email/life clearing (switchboard),
ecology graph churning (shadow mapper), research/session processing
(hearth), calendar event rendering (OMA), and command/query
processing (omnibox). The convergence across five unrelated domains
confirms the protocol is a natural joint — it exists because the
constraint triple exists, not because anyone designed it.

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
