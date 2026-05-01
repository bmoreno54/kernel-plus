# Thermal Rendering Contract — Trunk Protocol

**Status:** Active (promoted from five-fold convergence, 2026-04-25)
**Tags:** #kernel+ #trunk #protocol

## Principle

Any system that renders heterogeneous items at variable resolution under finite attention decomposes rendering into four independent axes and composes them into a contract that derives at encounter time.

The four axes:

1. **Categorical identity** — what kind of thing is this? (discrete, stable)
2. **Temporal intensity** — how alive is it? (continuous, decays, derives from engagement history)
3. **Estimated attention (DOI)** — how much cognitive resource is the observer allocating here? (continuous, derives from proxy signals at encounter time)
4. **Proxemic distance (zone)** — how far from the center of attention? (continuous, spatial or conceptual)

The rendering contract: `render(item) = f(category, intensity, doi, zone)`

Each axis is orthogonal. A hot item far from focus glows but renders small. A cold item at intimate range renders large but dim. The independence is structural — collapsing any two axes into one loses information the system needs.

## Axis Independence

- **Category is not intensity.** A work event and a personal event at the same heat level look different (category) but share urgency behavior (intensity).
- **Intensity is not DOI.** An item can be highly active (hot) but irrelevant to the current focus (low DOI), or dormant (cold) but exactly what was searched for (high DOI).
- **DOI is not zone.** Estimated attention is computed from proxy signals (query, navigation, interaction history). Proxemic zone is computed from topological distance. They correlate but are not identical — a search can surface a distant item at high DOI.

## DOI as Proxy Variable

DOI (Degree of Interest, Furnas 1986) is not a rendering primitive. It is a proxy variable for a latent quantity: how much cognitive resource the observer is allocating to each entity. The original formulation — `DOI(x, focus) = API(x) - D(x, focus)` — treats distance-from-focus as the primary signal. But distance is just the cheapest available proxy for the thing that actually matters: attention.

Multiple proxy signals can estimate the same latent variable:

- **Temporal distance** — how far in time from the focal moment (calendar surfaces)
- **Structural depth** — how far in a hierarchy from the focused node (tree/graph surfaces)
- **Frecency** — how often and recently engaged (interaction-history surfaces)
- **Cursor proximity** — how close the pointing device is (spatial interfaces)
- **Content classification** — how attention-worthy the content is (triage surfaces)

All produce the same type of output: a scalar that feeds into the zone classifier, which produces rendering, frame rate, and interaction contracts. The zone contract is signal-agnostic on its output side (zone → attributes, regardless of what computed the zone). The proxy variable principle makes the input side signal-agnostic too: any function `f(entity, focus) → scalar` that estimates attention allocation is a valid DOI signal.

This reframing is constraint-forced by: finite display space + finite cognitive bandwidth + unbounded content. Given those three constraints, DOI-as-proxy-variable is the only architecture that doesn't either (a) paginate (losing context) or (b) render everything uniformly (overwhelming attention).

The proxy signals don't just operate independently. They can fuse: `attention_estimate = Σ(wᵢ · signalᵢ)`. No implementation does this yet — each surface uses one or two signals. But the architecture implies it: any surface COULD accept multiple proxy signals and produce a fused attention estimate. The fusion weights are surface-specific (a calendar weights temporal distance heavily; an omnibox weights frecency heavily), but the fusion architecture is shared. The general form: `AttentionEstimator(signals: ProxySignal[]) → heat: float`.

Six independent implementations across the ecology compute DOI from different proxy signals and feed the result into the same zone-gated rendering pipeline. The convergence confirms that DOI-as-proxy-variable is a natural joint — it exists because the constraint triple exists, not because anyone designed it.

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

The rendering contract derives at encounter time. No axis is stored as "rendering state." Category is a property of the item. Intensity derives from engagement history. DOI derives from available proxy signals at the moment of the attention act. Zone derives from topological position. All four are computable from current state at the moment the surface renders.

This is the mechanism layer of the cold computation commitment: the rendering contract IS the cold derivation, applied to perception. The proxy variable architecture strengthens this: because DOI is estimated from whatever signals are available at encounter time, there is no warm DOI state to maintain. A new proxy signal (gaze tracking, scroll velocity, typing cadence) can be added without changing any stored state — it simply joins the estimation at runtime.

## Convergence Evidence

Six independent implementations across different domains computed the same four-axis decomposition without referencing each other. The convergence is the strongest evidence the pattern is structural rather than stylistic — it is what any attention-aware rendering system requires. The DOI-as-proxy-variable finding adds a second convergence dimension: not only do all implementations use the same four axes, they all estimate attention from different proxy signals and feed the estimate into the same zone-gated pipeline.

## Corroboration

Furnas DOI (1986), Hall proxemics (1966), Greenberg proxemic interaction (2010), Gibson ecological optics (1979), Bederson zoomable interfaces (1994). The four-axis structure was not derived from theory — it was discovered independently in practice, then recognized as convergent with these traditions. The proxy variable reframing finds additional corroboration in Symbiotik (arXiv 2511.11476), which uses direct neurophysiological measurement (EEG mental workload) to drive the same visualization adaptation that DOI drives from cheaper proxy signals — confirming that DOI estimates a real latent quantity, not an arbitrary metric.
