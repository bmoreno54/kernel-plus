# Agent Adapter Specification

## The Antipattern

`CLAUDE.md` as a filename ties the kernel's instruction surface to a specific agent platform. The ecology's sovereignty is compromised when its own configuration files bear another entity's brand. The kernel should name its own surfaces.

## The Solution

**`KERNEL.md`** becomes the canonical sovereign instruction surface — the routing header that orients any agent entering the ecology. Platform-specific files are **adapter emanations**: generated discovery mechanisms that point back to KERNEL.md.

The relationship: `KERNEL.md` (sovereign) → adapter script → platform files (generated)

## Platform Convention Survey

| Platform | File | Discovery |
|---|---|---|
| Claude Code | `CLAUDE.md` | auto-discovered, markdown |
| Cursor | `.cursorrules` or `.cursor/rules/*.mdc` | auto-discovered |
| GitHub Copilot | `.github/copilot-instructions.md` | auto-discovered |
| Windsurf | `.windsurfrules` | auto-discovered || Cline/Roo Code | `.clinerules` | auto-discovered |
| Devin | `devin.md` | auto-discovered |
| Aider | `CONVENTIONS.md` | manually configured |
| Continue.dev | `.continuerules` | auto-discovered |
| Zed AI | `.rules` | auto-discovered |
| Amazon Q | `.amazonq/rules/*.md` | auto-discovered |
| ChatGPT | *(none)* | account-level custom instructions |
| OpenClaw | filesystem-native | reads workspace markdown directly |

## Adapter Generation Pattern

A script (or manual process) reads `KERNEL.md` and emits platform-specific files:

```
KERNEL.md → generate_adapters.sh → CLAUDE.md
                                  → .cursorrules
                                  → .github/copilot-instructions.md
                                  → .windsurfrules
                                  → .clinerules
                                  → devin.md
                                  → CONVENTIONS.md
                                  → .continuerules
                                  → .rules
                                  → .amazonq/rules/kernel.md
```
Each generated file contains a platform-appropriate preamble that includes or references the KERNEL.md content, formatted for that platform's conventions.

## Gitignore Strategy

Two valid approaches:

1. **`.gitignore` the adapters** — they're generated emanations, not source. The kernel repo only tracks `KERNEL.md` and the generation script. Each user runs the script for their platform.
2. **Commit as convenience** — check in all adapter files so users of any platform get immediate discovery without running a script. The tradeoff is maintenance burden when KERNEL.md changes.

Either way, `KERNEL.md` is the source of truth. Adapter files are downstream.

## The Deeper Insight

The adapter files are **discovery mechanisms**, not instruction surfaces. They exist because each platform has a different filename convention for auto-loading instructions. That's the only reason they exist.

The kernel documents themselves — `node.md`, `fade.md`, `omnibus.md`, etc. — **ARE the instructions**. An agent that reads them understands the ecology. `KERNEL.md` is a routing header that tells the agent where to look and how to orient. The platform files are just the doorbell that gets the agent to read the routing header.

The implication: as platforms converge on reading workspace markdown (OpenClaw already does this natively), the adapter layer thins toward zero. The kernel's own documents become directly legible. The adapters are scaffolding for a transitional period where platforms haven't yet learned to read a workspace on its own terms.