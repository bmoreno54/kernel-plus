# Occlusion Rendering — Trunk Protocol

**Status:** Candidate (promoted from hearth session 2026-04-24)
**Tags:** #kernel+ #trunk #protocol #us #navigator

## Principle

Render situated subjectivity through environmental occlusion, not objective mapping. The user is always HERE. Everything else is positioned relative to that embodied center. Things nearby are detailed and interactive. Things further are compressed, ambiguous, partially visible. Things beyond draw distance don't render.

This is not a visual effect — it's a UX ontology. Every surface in the ecology that shows the user "where things are" should obey occlusion physics.

## Modular Across Sensory Channels

Occlusion has different mechanics per sensory channel:
- **Visual**: distance → apparent size, detail resolution, color saturation, overlap
- **Acoustic**: distance → wave interference, intensity attenuation, spectral filtering
- **Temporal**: distance from NOW → event detail, urgency saturation
- Each channel is an independent haptic field in the affordant stack shared by computers and humans

## Proxemic Zones (Hall 1966, Greenberg 2010)

| Zone | Depth | Rendering |
|------|-------|-----------|
| Intimate | 0-1 | Full detail, full color, interactive |
| Personal | 2 | Visible but compressed, expandable on demand |
| Social | 3 | Shapes/clusters, not individuals |
| Public | 4+ | Beyond draw distance, not rendered |

## Mathematical Foundation

Furnas DOI: `DOI(x) = API(x) - D(x, focus)`. Display iff `DOI >= k`.

Continuous proxemic sigmoid: `level(d) = 1 / (1 + e^(a(d-c)))`.

Apparent size: `size(x) = max(0.3, DOI(x))`.

## Pattern Respect

If the interface uses spatial metaphors, it MUST obey spatial rules:
- Occlusion is consistent (if A hides B, approaching B reveals it predictably)
- Scale is monotonic (closer = bigger, always)
- Transitions are continuous (nodes breathe, don't teleport)
- Violation of learned perceptual patterns causes ontomechanical frustration

## Seamless Multi-Modal Navigation

Any navigation mode that updates player_position on the same topology is compatible with every other mode without UX seams. The topology is the invariant; the input mode is the variable.

## Corroboration

Gibson (1979), Merleau-Ponty (1945), Hall (1966), Furnas (1986), Bederson (1994), Lamping & Rao (1995), Begault/NASA (1994), Norman (1988), Wickens (1995).
