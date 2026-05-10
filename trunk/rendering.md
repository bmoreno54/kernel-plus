# DOI Rendering Primitive — Trunk Specification

> **scope:** trunk — inherited by all surfaces that render collections
> with varying relevance
> **status:** active

## The Primitive

Any surface that renders a collection of items with varying relevance
to a focal point implements the same pipeline:

```
DOIRenderer {
  doi(item, focus): float                    // surface-specific distance metric
  zone(doi_value): Zone                       // shared: zone field classification
  attributes(zone, scale, thermal): AttrSet   // shared: zone-gated properties
  cluster(items): ClusterEntity               // shared: aggregate with dissolution
  probe(cursor, item): float                  // shared: Fitts'-optimal acquisition
}
```

**Surface-specific:** the `doi()` function. Each surface defines its own
distance metric and importance function. The metric varies — tree depth,
temporal hours, spatial pixels, network hops — but the output is always
a scalar in [0, 1].

**Shared:** everything else. Zone classification, attribute interpolation,
cluster dissolution, probe boosting — same mechanism regardless of metric.

## The DOI Function

Furnas (1986) Degree of Interest: `DOI(x, focus) = API(x) - D(x, focus)`

- **API(x)** — a priori importance. Intrinsic relevance independent of
  focus. A scalar: "how much does this item matter regardless of where
  you're looking?"
- **D(x, focus)** — distance from the current focus point. Surface-specific
  metric, normalized to produce DOI in [0, 1].

### Thermal Modulation

DOI alone is static. A thermal gradient provides secondary modulation:

- **Recency** — recently touched items run hotter
- **Engagement heat** — interacted items accumulate energy (frecency)
- **Staleness** — untouched items cool toward ambient

Thermal energy feeds into API(x), elevating baseline DOI for hot items.

## Zone Classification

Four proxemic zones (Hall 1966), classified by Gaussian membership:

| Zone | DOI Range | Character | Rendering |
|------|-----------|-----------|-----------|
| **Intimate** | 0.7–1.0 | Full engagement. All detail. | Maximum |
| **Personal** | 0.45–0.7 | Reduced but present. Key attributes visible. | High |
| **Social** | 0.2–0.45 | Peripheral. Aggregate rendering. | Low |
| **Public** | 0.0–0.2 | Beyond draw distance. Ambient or pruned. | None |

Zone boundaries are soft (Gaussian, not hard thresholds). Items can have
partial membership in two adjacent zones, enabling smooth transitions.

### Zone-Gated Attributes

Each zone determines a bundle of rendering properties:

```
AttrSet {
  visual:  { size, opacity, saturation, detail, breath_amplitude }
  click:   { action_type, zoom_params }
  hover:   { tooltip_tier, content_density }
  render:  { which_fields, label_truncation, icon_vs_text }
}
```

The zone determines not just what you SEE but what CLICKING DOES and
what HOVERING SHOWS. Three-layer rendering contract: visual + click
dispatch + hover dispatch.

## Poincaré Apparent Size

DOI maps to visual size through hyperbolic geometry (Poincaré disk model).
Items near focus are large; far items compress hyperbolically. Matches
spatial cognition.

### Per-Element Decay

Importance modulates steepness of the Poincaré curve:

- High-importance: gentler decay → maintain presence at greater distances
- Low-importance: steeper decay → compress faster into background

Steepness: `1.0 + (1.0 - importance) * 0.8` (range 1.0 to 1.8).

## Cluster-as-Entity Rendering

When multiple items share a grouping relationship, they render as a single
aggregate entity at social/public distance, dissolving into individuals
as DOI increases:

```
ClusterEntity {
  members: Item[]
  center: FocusCoordinate
  importance: float       // max of member importance
  dissolution: float      // 0.0=clustered, 1.0=dissolved

  // DOI < 0.45  → dissolution = 0.0 (cluster only)
  // DOI 0.45–0.65 → interpolates (transition zone)
  // DOI > 0.65  → dissolution = 1.0 (individuals only)
}
```

Clusters are first-class rendered entities, not compression hacks.

## Fitts'-Optimal Probe

Cursor probe scales with distance from focus:

- Nearby items: narrow probe σ (already easy to acquire)
- Distant items: wider probe σ (need acquisition help)

Scale: `1.0 + log₂(1 + distFromFocus / referenceUnit) × 0.3`

Fitts' Law in DOI-space: distant items have higher interaction cost,
so the system compensates by widening their acquisition catchment.
Capped at 2.5× base σ.

## Relationship to Other Trunk Protocols

- **FADE** provides the discovery methodology — this primitive was found
  through FADE applied to independent implementations that converged.
- **Omnibus** provides coordination: `#rendering #doi #proxemics #cluster
  #probe #thermal #frecency #kernel+`
- **Cold computation** — DOI is derived at encounter time from observer
  position, never stored as warm state. This IS cold computation applied
  to rendering.
- **Opportunistic separation** — this primitive separated from its first
  implementation when convergence with a second was documented.

## Generality

This protocol passes the veil of ignorance: any system that renders a
collection of items with varying relevance needs this pipeline. Email
clients, file browsers, code editors, music libraries, social feeds,
dashboards — all face the same problem: too many things, finite attention,
need for situated relevance ordering.
