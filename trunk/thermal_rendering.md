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

## Cold by Constitution

The rendering contract derives at encounter time. No axis is stored as "rendering state." Category is a property of the item. Intensity derives from engagement history. DOI derives from the current attention act. Zone derives from topological position. All four are computable from current state at the moment the surface renders.

This is the mechanism layer of the cold computation commitment: the rendering contract IS the cold derivation, applied to perception.

## Convergence Evidence

Five independent implementations across different domains computed the same four-axis decomposition without referencing each other. The convergence is the strongest evidence the pattern is structural rather than stylistic — it is what any attention-aware rendering system requires.

## Corroboration

Furnas DOI (1986), Hall proxemics (1966), Greenberg proxemic interaction (2010), Gibson ecological optics (1979), Bederson zoomable interfaces (1994). The four-axis structure was not derived from theory — it was discovered independently in practice, then recognized as convergent with these traditions.
