# Kernel+ Harvest 002: Latent Extractions

**Date:** 2026-04-23
**Method:** Second-pass harvest — domain-specific implementation details that imply unstated general principles, now made explicit. Where harvest_001 found atoms already stated in general terms, this harvest finds atoms hiding inside domain particulars.
**Source ecology:** infinity-engine, skyrim/companion, weird-city, road, hearth, data-sovereignty
**Atoms found:** 47
**Veil test:** Each atom was extracted by asking: "What general principle does this domain-specific detail teach, such that someone with no knowledge of the domain would still recognize the structural insight?"

---

## Perception & Information Scarcity

- **Darkness/fog-of-war as information scarcity that creates decision texture.** Withholding information isn't absence — it's a design material that gives choices weight.
- **Pixel art as information-dense rendering — constraints force signal compression.** When bandwidth is scarce, every signal carries more. Constraint is a clarity engine.
- **Status summaries should be derived at read-time, never stored.** Stored summaries drift from reality. Compute the summary when someone asks for it.
- **The test for subjective systems is whether the subject would recognize themselves.** If the model's output surprises its subject in a way they'd reject, the model is wrong.

## Systems & Engagement Economics

- **Systems should tax engagement, not elapsed time.** Cost what the agent does, not how long they exist. Time-tax punishes presence; engagement-tax rewards participation.
- **Thermodynamic metaphor: energy conservation across system state changes.** When one thing changes, trace where the energy went. Nothing is free; everything transforms.
- **Thermal gradient as universal engagement model.** Cold = untouched, hot = deeply engaged. The gradient itself is readable state.
- **Fountains as bounded regeneration — the system gives but within designed limits.** Renewal is architectural. Unlimited giving collapses the economy; bounded giving sustains it.
- **Gathering/harvesting as the prototypical player-world transaction.** The simplest meaningful exchange: agent reaches into world, world yields something, both are changed.

## Input & Resolution

- **Input should cascade through increasingly expensive resolvers.** Try the cheap interpretation first. Escalate only when ambiguity survives.
- **Unresolved user intent is a design signal, not a failure.** When the system can't parse what someone wants, that's data about a gap — not user error.
- **When multiple input modalities exist, unify their semantic layer.** Hands, voice, gaze — the system sees verbs and nouns, never raw input.
- **Affordance menus should be generated from live system state, not hardcoded.** What you can do should reflect what's actually possible right now, not what was possible when the menu was written.

## Identity & Composition

- **Narrative identity emerges from accumulated mechanical choices, not declared backstory.** You are what you did, not what you said you'd be.
- **Reputation systems should track behavioral evidence, not assign categorical labels.** "You killed 3 guards" is data. "You are evil" is interpretation that forecloses.
- **Meta-observations must not re-enter the system as first-order inputs.** Watching the game is not playing the game. Meta-level awareness that feeds back into the base system creates runaway loops.
- **Geometric mean penalizes lopsidedness for composite evaluation.** When combining scores, the geometric mean ensures you can't compensate for a zero in one dimension with excellence in another.
- **Domain primitives should be discovered through use, not declared in advance.** The right abstractions emerge from doing the work. Premature taxonomy kills what it names.

## Architecture & Topology

- **Plateau as stable play surface vs. progression as movement between plateaus.** Stability is the thing. Movement between stable states is the interesting transition. Design the plateaus first, then the ramps.
- **Encounter design as structured surprise within bounded possibility.** The trellis provides context; the vines provide surprise. Neither alone is enough.
- **Inventory as attention management, not object storage.** What you carry is what you're paying attention to. The bag is a lens, not a container.

## Integration & Boundaries

- **Exhaustive fail-open contract at integration boundaries.** At every seam where two systems meet, enumerate every failure mode and ensure the default is "keep running," not "halt."
- **MO2 virtual filesystem as sandboxed composition model.** Layer modifications without touching the base. The virtual layer IS the composition — the original stays pristine.
- **Mod overwrite priority as layered precedence with last-writer-wins.** When multiple layers claim the same target, the last one in the stack wins. Explicit ordering replaces implicit conflict.
- **Load order as dependency graph with conflict resolution semantics.** Dependencies form a DAG. Conflict resolution is the interesting part — not whether things connect, but what happens when they disagree.
- **Synthesis patching as programmatic conflict resolution.** When layers conflict, a programmatic resolver can read all claims and produce a merged output no manual process could maintain.
- **Snapshot/restore as first-class development operation.** If you can't checkpoint and rollback, you can't experiment. Make the save/load loop as cheap as possible.
- **When the fix requires disabling infrastructure, re-examine the diagnosis.** If the "solution" is to turn off a core system, the problem is probably somewhere else.

## Behavioral Composition

- **Papyrus script attachment as behavioral composition without inheritance.** Attach behaviors to entities without class hierarchies. The entity is what its scripts do, not what class it inherits from.
- **The companion as autonomous agent with bounded sovereignty in shared world.** An agent that acts on its own judgment within limits the sovereign sets. Not a puppet, not independent — bounded.
- **FOMOD decision trees as user-facing configuration surfaces.** Expose system configuration as guided choice trees. The user makes decisions; the system enacts them.
- **Layered constitution with independent timescales.** Cultural identity changes over years, disposition over weeks, emotion over minutes, situation over seconds. Each layer has its own clock.
- **History is calculated, not stored — dark actor crystallization.** Don't store a history log; derive what must have happened from current state. The past is a function of the present.

## Observability & Process

- **Live monitoring as continuous observability during system operation.** Don't wait for the crash report. Watch the system breathe in real time.
- **Camp as readable artifact of offscreen state.** When something happens where you can't see it, leave a readable trace. The artifact IS the communication.

## Sovereignty & Boundaries

- **Vocabulary quarantine as sovereignty mechanism.** Foreign vocabulary entering your system can colonize your thinking. Airlock it. Examine it. Translate on your terms.
- **Ephemeral tokens at boundary crossings.** Signals that cross domain boundaries carry only what the interface requires — stripped of private content, carrying provenance, expiring after use.
- **The sovereign chooses what crosses their boundary.** Default: nothing gets out without consent. Not paranoia — architecture.
- **Pidgin density at contact zones — rough, gestural, oriented by feel.** First contact between domains is always low-resolution. That's not failure; it's appropriate information density for the level of mutual understanding.
- **Accumulated practice hardens pidgin into creole.** Repeated boundary crossings thicken the shared language. What was rough gesture becomes reliable grammar. The thickness is earned, not designed.

## Data & Knowledge

- **Behavioral vs. reflective data as complementary registers.** What someone does and what someone says about what they do are different data streams. Neither alone is complete. Together they triangulate.
- **Watermill surplus — transactions producing data as byproduct.** Every engagement transaction produces data exhaust. Capture it at the moment of generation, not as a separate surveillance operation.
- **Session boundaries as natural checkpointing opportunities.** The natural rhythm of engagement (start, work, stop) provides free checkpointing surfaces. Don't fight the rhythm; instrument it.

## Meta-Kernel & Ecology

- **The ecology as rhizome — no privileged root, growth from any node.** No document contains the others. No node is primary. Meaning co-constitutes through mutual reference.
- **Fiction as architectural threat modeling.** Fictional adversaries and failure scenarios are safe contexts for exploring real architectural vulnerabilities.
- **Deliberate deferral as sensing mechanism.** Not deciding yet is itself a decision — one that preserves optionality and lets more signal accumulate before committing.
- **FADE as fractal — applies identically at sentence scale and system scale.** The same four operations (Find, Analyze, Decompose, Exploit) work on a single dependency or an entire paradigm. Scale-invariant methodology.

---

## Source Manifest

| Domain | Files Annotated | Atoms |
|--------|----------------|-------|
| infinity-engine | 12 files (fade_*, design_card_*, research_fade_*) | 20 |
| skyrim/companion | 11 files (companion/docs, notes, research, operations, tools) | 14 |
| road | 5 files (trunk/fade, omnibus, sovereignty_posture, decomposition, procedural_memory; notes/fade_pidgin_creole) | 6 |
| hearth | 2 files (research/pidgin_private_project_pattern, research/cards/fade_weird_city_intersection) | 2 |
| weird-city | 1 file (CLAUDE.md) | 1 |
| data-sovereignty | 1 file (CLAUDE.md) | 2 |
| notes/fade_translation_surfaces | 1 file | 1 |
| **Total** | **33 files** | **47** |

## Relationship to Harvest 001

Harvest 001 found 74 atoms already stated in general terms — material that passed the veil of ignorance without translation. This harvest found 47 atoms that required extraction: the domain-specific detail was load-bearing, but the general principle was implicit. The extraction IS the kernel+ contribution — making the latent explicit.

Combined kernel+ corpus: **121 atoms** across two harvests.
