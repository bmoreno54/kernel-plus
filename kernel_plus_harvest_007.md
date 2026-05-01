# Kernel+ Harvest 007: Fifth Nightly Compilation

**Date:** 2026-05-01
**Method:** Fifth nightly compiler run. Material sourced from mapper run 18 (2026-05-01) and 13 hearth signals (2026-05-01). Previous harvests: 001 (74 atoms), 002 (47 atoms), 003 (6 atoms), 004 (6 atoms), 005 (4 atoms), 006 (3 atoms). Previous compilation: v7 (clearing protocol thickens cold computation).
**Source ecology:** shadow_mapper/analyses (run 18), hearth/signals (2026-05-01)
**Atoms evaluated:** 5 new candidates
**Atoms passed veil:** 1 (integrated), 4 harvest-grade
**Atoms integrated into structure:** 1 (trunk thickening)
**Atoms deferred:** 4 (harvest-grade, recorded below)
**Atoms rejected:** 0

---

## Integrated: Trunk Thickening — DOI as Proxy Variable

### Latent Attention Estimation → thickened `trunk/thermal_rendering.md`

**Source:** Shadow mapper Run 18 (`analyses/doi-proxy-variable-latent-attention-kernel-plus.md`)

**Domain-independent form:** DOI is not a rendering primitive — it is a proxy variable for a latent quantity: how much cognitive resource the observer is allocating to each entity. Any system rendering heterogeneous items under finite attention must estimate this latent variable. The estimation can use any available signal — spatial distance, temporal distance, interaction history, content salience, physiological measurement. Multiple proxy signals can fuse into a single attention estimate. The zone contract that consumes the estimate is signal-agnostic on both input and output sides.

**Evidence:** Six independent implementations across the ecology compute DOI from different proxy signals (temporal distance, tree depth, frecency, cursor proximity, content classification) and feed the result into the same zone-gated rendering pipeline. External validation from Symbiotik (arXiv 2511.11476) confirms via EEG that DOI estimates a real latent quantity.

**Veil test:** PASS. The principle that rendering fidelity should be driven by estimated cognitive resource allocation, using whatever proxy signals are available, applies to any attention-mediated interface. The constraint triple (finite display + finite cognition + unbounded content) is universal.

**Integration:** Added "DOI as Proxy Variable" section to thermal_rendering.md between Axis Independence and Zone Determines Interaction Affordance. Updated axis 3 description from "focal relevance" to "estimated attention." Updated Cold by Constitution to note proxy architecture strengthens cold commitment. Updated Convergence Evidence to note second convergence dimension (signal diversity). Updated Corroboration with Symbiotik reference.

---

## Harvest-Grade Atoms (Pass Veil, Not Yet Positional)

### Three-Layer Zone Contract

**Source:** Hearth signal (`signals/convergence_three_layer_zone_contract_2026-05-01.md`)

**Domain-independent form:** The zone field gates three independent output contracts: rendering (what it looks like), frame rate (how often it updates), and interaction (what the user can do). All three are functions of the same zone computation. The type: `ZoneContract = {rendering: Zone → AttributeSet, frameRate: Zone × MaskingFactors → SkipRate, interaction: Zone → InteractionModality}`.

**Veil test:** PASS. Any attention-gated system needs all three contracts — rendering alone produces pretty but inert surfaces, interaction alone produces responsive but visually undifferentiated ones. The three-layer composition is the minimal complete response. But: the rendering and interaction layers are already in thermal_rendering.md. The frame rate contract is genuinely new but needs fuller analysis — is it a structural necessity or a performance optimization? Apple visionOS shipping the same pattern is evidence for structural necessity. Recording as harvest-grade pending analysis of the frame rate contract's independence.

### Perceptual Clustering (Entity Identity at Distance)

**Source:** Hearth signal (`signals/convergence_perceptual_clustering_2026-05-01.md`)

**Domain-independent form:** DOI governs not just how entities render but when multiple entities merge into one entity. At a given observation distance, perceptual equivalence determines grouping — two things that look the same from far away ARE the same from far away. This is distinct from attribute-set rendering (which governs which properties render) and from the rendering contract (which governs how). It governs ENTITY IDENTITY at distance.

**Veil test:** PASS. The principle that observation distance determines entity identity is domain-independent — it applies to geographic maps, org charts, search results, any collection viewed at varying resolution. But: the principle is stated in one paragraph with three domain examples. It needs dedicated analysis to determine whether it's a new position or a corollary of the property inclusion layer (entity-level gating is already described as "recurrence compression" in the three-layer stack). Recording as harvest-grade.

### JND Masking Convergence

**Source:** Hearth signal (`signals/2026-05-01_convergence_jnd_trunk.md`)

**Domain-independent form:** Skip computation when perceptual delta is below a just-noticeable-difference threshold. The threshold is adaptive — it rises under masking (fast scroll, fast typing, animation). Three surfaces implement it independently. The general form: `perceptualThreshold(baseThreshold, maskingIntensity) → skipRate`.

**Veil test:** PASS. Any rendering system facing finite compute and finite perception will develop perceptual thresholding. But: this is an optimization principle already implicit in the zone-gated rendering pipeline (public zone items are already below threshold by definition). The adaptive masking dimension is new but needs fuller analysis. Recording as harvest-grade.

### Forced Discontinuity in Repeated Sampling (Coprime Scheduling)

**Source:** Hearth signal (`signals/2026-05-01_scheduling_architecture_coprime.md`)

**Domain-independent form:** Any system that repeatedly samples a complex space will converge on familiar attractors unless it employs forced discontinuity in its sampling strategy. Two mechanisms: (1) temporal coprime scheduling — tasks at non-divisible intervals with staggered offsets, maximal phase separation, so no two passes align; (2) disposition matrix — forced mode-switching across a combinatorial space of agentic modalities, with an anti-convergence log preventing re-encounter. This is the temporal equivalent of occlusion — no fixed viewpoint, every encounter is fresh.

**Veil test:** PASS. The anti-attractor principle applies to any recurring sampling process — academic peer review (rotating reviewers), crop rotation, job rotation, portfolio rebalancing. The constraint: repeated sampling + finite attention + complex space → attractor collapse without forced discontinuity. But: not yet mapper-analyzed or tagged #kernel+. The principle emerged from a specific scheduling restructuring, not from cross-ecology convergence. Recording as harvest-grade pending mapper analysis.

---

## What the Kernel Looks Like Now

### Positions (kernel/)
- `node.md` — sovereignty
- `relation.md` — intersubjectivity
- `provenance.md` — deterministic origin + vocabulary migration
- `node_schema.md` — molecular composition + hashability asymmetry
- `schema.md` — emergent self-description

### Protocols (trunk/)
- `fade.md` — universal ingestion
- `noise_floor.md` — non-destructive attenuation
- `procedural_memory.md` — graveyard + gold
- `decomposition.md` — radically constructive middle-out
- `contextual_providence.md` — cross-pollination default
- `omnibus.md` — tag-based stigmergic coordination
- `opportunistic_separation.md` — greedy niche occupation
- `sovereignty_posture.md` — defensive/extractive/assertive
- `virtue_journey.md` — continuous situated discernment
- `cold_computation.md` — derive at encounter time + stigmergic statefulness + clearing protocol
- `occlusion_rendering.md` — situated subjectivity through environmental occlusion
- `thermal_rendering.md` — five-axis rendering stack + property inclusion + DOI as proxy variable (THICKENED)

### Harvest Provenance
- harvest_001: 74 atoms (general terms)
- harvest_002: 47 atoms (latent extractions)
- harvest_003: 6 atoms passed veil
- harvest_004: 6 atoms passed veil
- harvest_005: 4 atoms passed veil
- harvest_006: 3 atoms evaluated, 1 passed + integrated, 2 harvest-grade
- harvest_007: 5 atoms evaluated, 1 passed + integrated, 4 harvest-grade (this document)
- **Total corpus: 145 atoms**, 12 trunk protocols, 5 kernel positions

### Pending Harvest-Grade (cumulative)
- Epigenetic validation (LLM three-zone boundary) — from harvest_004
- Laboratory function in ecologies — from harvest_004
- Reciprocal ludic-formal fertilization — from harvest_004
- Unconditional capture — from harvest_002
- Unresolved intent as signal — from harvest_002
- Convergence as trunk readiness — from harvest_005
- Rendering contract two-phase signature — from harvest_006
- Directional trust asymmetry — from harvest_006
- **Three-layer zone contract** — NEW from this compilation
- **Perceptual clustering (entity identity at distance)** — NEW from this compilation
- **JND masking convergence** — NEW from this compilation
- **Forced discontinuity in repeated sampling** — NEW from this compilation
