# Proxy Sovereignty — Network Boundary Architecture

> **scope:** trunk — inherited by all branches that interface with
> external networks or services
> **status:** active

## Principle

Sovereign systems should route all external contact through local bridge
servers. The bridge is the embassy: a controlled interface point where
foreign protocol meets domestic sovereignty.

Direct dependence on external APIs, services, or platforms creates a
sovereignty leak — the external system can change terms, deprecate
endpoints, introduce tracking, or disappear entirely. The proxy absorbs
these shocks.

## What the Proxy Handles

### Authentication Quarantine

External auth tokens, API keys, and session credentials live in the
proxy layer, never in the ecology's content nodes. If a service changes
its auth scheme, only the proxy needs updating. Content nodes never
reference external auth directly.

### Caching as Sovereignty

Data pulled through the proxy is cached locally. The cache is the
ecology's copy — sovereign, not borrowed. If the external service
disappears tomorrow, the cached data persists. Cache invalidation
is on the ecology's schedule, not the service's.

### API Deprecation Absorption

External APIs change. Endpoints move. Schemas evolve. The proxy
translates between the ecology's stable internal vocabulary and
whatever the external service currently demands. The ecology's nodes
never need to update when an external API changes — only the proxy's
translation layer.

### Cross-Device Consistency

A local bridge server accessible via mesh network (Tailscale, LAN,
etc.) provides the same interface regardless of which device is
requesting. Phone, laptop, tablet — all hit the same proxy, get the
same data, through the same sovereignty boundary.

## Architecture

```
ecology node → proxy (local) → external service
     ↑              |
     └── cache ←────┘
```

The proxy is a local process. It lives on your infrastructure. It
answers to you. External services are tenants of the socket — the
current occupant is not the architecture (see sovereignty_posture.md,
"the socket model").

## Relationship to Sovereignty Posture

Proxy sovereignty extends the three modes:

- **Defensive:** The proxy blocks outflow of ecology data to external
  services (no telemetry, no usage data, no metadata leakage)
- **Extractive:** The proxy pulls data from external services into
  local cache (your data comes home)
- **Assertive:** The proxy establishes the ecology's endpoint as
  primary — external services receive what the ecology chooses to
  emit, in the format the ecology chooses

## Implementation Notes

The proxy can be:
- A local HTTP server
- A CLI wrapper around API calls
- A message queue with local persistence
- A reverse proxy with caching headers

The shape doesn't matter. What matters: the ecology never makes a
direct outbound call to an external service from a content node.
All outbound traffic routes through a sovereignty-aware intermediary
that caches, translates, and controls.

## When This Applies

Any time your ecology needs to:
- Pull data from an API (RSS feeds, social media, databases)
- Push data to an external service (publishing, syncing)
- Authenticate against a third-party system
- Depend on any service you don't control

If you can't run it yourself, route it through something you can.
