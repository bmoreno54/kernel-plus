# Thermal Rendering Contract — Trunk Protocol

**Status:** Active (promoted from five-fold convergence, 2026-04-25)
**Tags:** #kernel+ #trunk #protocol

## Principle

Any system that renders heterogeneous items at variable resolution under finite attention decomposes rendering into four independent axes and composes them into a contract that derives at encounter time.

The four axes:

1. **Categorical identity** — what kind of thing is this? (discrete, stable)
2. **Temporal intensity** — how alive is it? (continuous, decays, derives from engagement history)
3. **Focal relevance (DOI)** — how relevant to the current attention act? (continuous, derives at query/encounter time)
4. **Proxemic distance (zone)** — how far from the center of attention? (continuous, spatial or conceptual)

The rendering contract: `render(item) = f(category, intensity, doi, zone)`

Each axis is orthogonal. A hot item far from focus glows but renders small. A cold item at intimate range renders large but dim. The independence is structural — collapsing any two axes into one loses information the system needs.

## Axis Independence

- **Category is not intensity.** A work event and a personal event at the same heat level look different (category) but share urgency behavior (intensity).
- **Intensity is not DOI.** An item can be highly active (hot) but irrelevant to the current focus (low DOI), or dormant (cold) but exactly what was searched for (high DOI).
- **DOI is not zone.** Focal relevance is computed from the attention act (query, navigation, gaze). Proxemic zone is computed from topological distance. They correlate but are not identical — a search can surface a distant item at high DOI.

## Zone Determines Interaction Affordance

Proxemic zones (after Hall 1966) determine not just visual rendering but what the user can DO with the item:

| Zone | Depth | Rendering | Interaction |
|------|-------|-----------|-------------|
| Intimate | 0-1 | Full detail, vivid, animated | Manipulate, edit, expand |
| Personal | 2 | Visible but compressed | Preview, select, expand on demand |
| Social | 3 | Shapes/clusters, not individuals | Navigate to, aggregate view |
| Public | 4+ | Beyond draw distance | Warp/teleport only |

The zone boundary is continuous (sigmoid), not discrete. The table names the qualitative regions of a gradient.

## Temporal Directionality

The four rendering axes operate within a temporal field that is itself asymmetric. Prospective resources (rendering warmth, priority, relevance) intensify toward the future — toward where action happens. Retrospective resources (knowledge, provenance, topological weight) accumulate toward the past — toward where understanding crystallizes.

The "now" boundary is a phase transition, not merely a position marker. On one side, items are rendered with heat (forward resources dominating). On the other, items are rendered with depth (backward resources dominating). Past items retain presence — enough backward resource to inform current decisions, not enough to compete with forward items for attention.

This asymmetry is structural. Any attention-allocation system operating on a temporal axis must develop it: total suppression of the past loses information; equal treatment of past and future loses temporal agency. The rendering contract encodes this as temporal polarity — a fifth parameter that modulates the four axes according to an item's position relative to the now-boundary.

The bidirectional model composes with the four axes rather than replacing them. Category, intensity, DOI, and zone remain orthogonal. Temporal polarity determines which gradient dominates: forward items warm through intensity and DOI; backward items cool but thicken through provenance and accumulated relational weight. The contract becomes: `render(item) = f(category, intensity, doi, zone, temporalPolarity)`.

## Property Inclusion — The Discontinuous Layer

The four rendering axes govern *how* visible properties render — scale, opacity, color, position. But zone boundaries also gate *which* properties are visible at all. This is a phase transition in the contract's architecture.

A system that only varies rendering intensity is continuous — everything present, scaled. A system that varies property inclusion is discontinuous — properties appear and disappear at zone boundaries. The zone boundaries become phase transitions where the information topology changes, not just the information density.

This is information-theoretic necessity, not design choice. A system that only scales faces an information density floor: at sufficient distance, even minimal rendering carries more information than the observer can metabolize. The response is to drop properties entirely — the same reason LOD (Level of Detail) systems switch meshes rather than scaling vertices. Continuous degradation hits a floor where discrete simplification is the only path. The attribute set IS the information-theoretic LOD.

The rendering contract is therefore a three-layer system:

1. **Data preparation** — recurrence compression, rhythm detection (entity-level gating: repeated entities lose individual identity, replaced by aggregate rhythm)
2. **Property inclusion** — attribute sets (property-level gating at zone boundaries: which properties exist in the output)
3. **Visual rendering** — the four-axis thermal contract (continuous scaling within included properties)

Each layer was independently discovered across multiple surfaces. No layer designed the others. The ecology grew this stack from the bottom up. The attribute set composes with pace entrainment: fewer properties at distant zones create the conditions for faster scanning rhythm — property inclusion gates WHAT; pace entrainment gates WHEN.

The counter-test: could a system avoid property gating entirely? Only if all properties are equally important at all distances — which holds only for homogeneous entities. The moment entities are heterogeneous (which they always are in practice), properties have different information value at different distances, and gating becomes necessary because the observation budget is finite.

## Cold by Constitution

The rendering contract derives at encounter time. No axis is stored as "rendering state." Category is a property of the item. Intensity derives from engagement history. DOI derives from the current attention act. Zone derives from topological position. All four are computable from current state at the moment the surface renders.

This is the mechanism layer of the cold computation commitment: the rendering contract IS the cold derivation, applied to perception.

## Convergence Evidence

Five independent implementations across different domains computed the same four-axis decomposition without referencing each other. The convergence is the strongest evidence the pattern is structural rather than stylistic — it is what any attention-aware rendering system requires.

## Corroboration

Furnas DOI (1986), Hall proxemics (1966), Greenberg proxemic interaction (2010), Gibson ecological optics (1979), Bederson zoomable interfaces (1994). The four-axis structure was not derived from theory — it was discovered independently in practice, then recognized as convergent with these traditions.
