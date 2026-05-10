# Procedural Memory — The Graveyard and the Gold

> **scope:** trunk — inherited by all branches
> **status:** active

## What Procedural Memory Is

Procedural memory is the ecosystem's accumulated knowledge about what works and what fails in practice. It is not theoretical — every entry exists because something was tried, and the outcome was observed.

The agent checks procedural memory before acting. If a Known Working Procedure exists for the current task, use it. If the task resembles a Graveyard entry, do not repeat the failure — find an alternative or ask the user.

When the agent discovers new procedural knowledge during any operation, it logs it here if the knowledge has cross-branch relevance, or in the branch's local procedural docs if it's branch-specific.

## The Graveyard — What Has Failed

Entries in the Graveyard are not recommendations to avoid forever. They are records of specific failures under specific conditions. If conditions change materially, a Graveyard entry can be re-evaluated. But the default is: do not retry a graveyard method without explicit reason to believe the failure condition has been resolved.

| Method | Failure | Conditions | Learned |
|---|---|---|---|
| Fabricating notes from assumption | Creates false confidence, masks real requirements | Any external resource | Always read from authoritative source docs (FADE Find phase) |

> new entries accrete from real operational friction.
> the table above is a seed; your ecology will fill it.

## The Gold — What Works Reliably

| Procedure | Context | Steps |
|---|---|---|
| (empty) | | |

> new entries accrete as the agent discovers what works.
> every Gold entry exists because it was tested and confirmed.

## The Diagnostic Reflex

When the agent encounters a failure during operation, before retrying or working around it:

1. **Check the Graveyard.** Is this a known failure pattern? If yes, use the documented alternative.
2. **If it's new, log it.** Record what was tried, what failed, and what the failure looked like. Be specific — "it didn't work" is not a Graveyard entry.
3. **If a workaround succeeds, log that too.** The workaround becomes a Gold entry.
4. **If the user has to correct the agent's approach, that correction becomes both a Graveyard entry (what was wrong) and a Gold entry (what the user directed instead).**

## Autonomous Self-Correction

If the user has to remind the agent to follow a procedural memory entry, the agent must immediately note this as a reinforcement signal. The goal is that the user never has to give the same correction twice. Persistent memory carries corrections across conversations. Procedural memory carries them across the ecosystem.
