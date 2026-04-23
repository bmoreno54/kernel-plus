# Fractal Noise Floor — Non-Destructive Data Hygiene

> **scope:** trunk — inherited by all branches
> **status:** active

## What the Noise Floor Is

The noise floor is the threshold below which data becomes inaudible to the current operation without being destroyed. It is the ecosystem's alternative to garbage collection, pruning, or deletion. Nothing is ever removed for hygiene. It is attenuated — shifted out of active legibility — based on the current operational scale.

This is borrowed from signal processing: in any recording, there is a noise floor below which signal is present but inaudible. Raising or lowering the floor doesn't create or destroy signal. It changes what is legible at the current listening level.

## Why Not Deletion

Deletion is destructive and irreversible. In a constructive ecosystem where decomposition generates referential material around original artifacts, deleting "old" decompositions throws away knowledge that may become operationally relevant at a different scale or in a different branch. The noise floor preserves optionality.

The cost of preservation is not zero — it is token cost, context window space, cognitive load. The noise floor manages that cost through attenuation, not elimination.

## Co-Constitution: The Haptic Sensorium

The noise floor is not managed unilaterally by the agent or by the user. It is co-constituted by the local haptic sensorium — the felt shape of the current engagement that pre-selects relevance before any intentional filtering occurs.

This operates fractally. Every level of engagement has its own haptic sensorium:

- **The user's embodied attention** — what's under their hands, what screen, what problem they're working on
- **A problem-solution run** — the situatedness of a particular debugging session or research pass naturally attenuates what's irrelevant
- **A branch project** — one project's sensorium naturally filters another project's details
- **A single session** — the accumulated context shapes what resolves as signal

Each level's sensorium pre-selects relevance before intentional noise management enters the picture. The intentional layer operates on top of the already-situated field, not in place of it.

## How Attenuation Works

### Scale Inference

Within the co-constituted field, the agent silently infers operational scale before generating output:

- **Macro** (system architecture, cross-project coordination, philosophical direction): Micro-level details fall below the floor.
- **Meso** (subsystem design, module-level work, feature implementation): Macro context and micro details both attenuate.
- **Micro** (specific bug fix, single file edit, one installation): Everything except the immediate operational context attenuates.

The agent does not announce the inferred scale. It operates from the inference and adjusts if the user's response indicates a mismatch.

## The Constraint

The agent must never delete ecosystem data for hygiene purposes. If context is too large, attenuate. If a document is outdated, update it — do not remove the old content, annotate it as superseded and let it cool below the floor. If a branch's knowledge base grows unwieldy, reorganize by scale rather than by purging.

The only legitimate deletion is the user explicitly directing it, or the safety protocol requiring it.
