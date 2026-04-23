# Sovereign Ecology Kernel

## What This Is

A personal ecosystem — a system for organizing projects, knowledge, and creative work that grows from your own friction rather than following someone else's categories. Built on a small set of structural commitments (the kernel) and operational protocols (the trunk) that together provide a substrate for any domain you bring to it.

The kernel was distilled from an ecology that proved these patterns across multiple unrelated domains — game development, web development, philosophical system-building, content generation, music production, hardware management. The domain-specific content was stripped through a veil of ignorance test. What remains is what generalizes.

Any agent opening this project should read this file first, then the kernel and trunk documents it references before engaging with work.

## The Alpha Entity

The person using this ecology is the zero-class entity — the sovereign origin of all intent, meaning, and validation. Constitutionally defined in `alpha_entity.md`.

What this means for any agent working here:

- The human originates direction. The agent extends reach.
- If authority hasn't been explicitly deferred and the agent is uncertain, stop and ask.
- Do not pre-calculate intent. The agent learns through friction, not pre-programming.
- Focus on grip (restating input to verify alignment) and negative space (mapping gaps and implications around what the human is pointing at).
- The human participates as situated judge, not spectator. During non-trivial tasks, regularly surface meaningful forks — not "what do you want?" but "here's the shape, which resonates?"
- **The harnessed human is the source of all general intelligence.** The kernel doesn't generate vitality — you do.

## The Kernel

Foundational structural commitments in `kernel/`. The minimal set of positions all projects inherit holographically:

| Document | Position |
|---|---|
| `kernel/node.md` | A node is sovereign. Readable alone, understood as what it is. |
| `kernel/relation.md` | A relation is intersubjective. Both sides describe it. Neither contains the other. |
| `kernel/provenance.md` | Provenance is deterministic. Who, when, from what. Structural facts. |
| `kernel/node_schema.md` | Molecular composition. What emerges when the three positions compose: sovereignty test, adapter boundary, holographic emanation. |
| `kernel/schema.md` | What the graph has discovered about itself. Emergent, not prescribed. |

## Trunk Protocols

Shared operating protocols inherited by all branches. Read them before doing branch-level work.

| Protocol | Document | What It Does |
|---|---|---|
| **FADE** | `trunk/fade.md` | Universal ingestion airlock. Find, Analyze, Decompose, Exploit. |
| **Noise Floor** | `trunk/noise_floor.md` | Non-destructive data hygiene. Attenuate by scope, never delete. |
| **Procedural Memory** | `trunk/procedural_memory.md` | Graveyard (what failed) and Gold (what works). Built from friction. |
| **Decomposition** | `trunk/decomposition.md` | Radically constructive. Originals stay intact. Middle-out, purpose-driven. |
| **Contextual Providence** | `trunk/contextual_providence.md` | Cross-pollination is default. Hard silos are not. |
| **Omnibus Tag Substrate** | `trunk/omnibus.md` | Tag-based semantic coordination. Tags carry meaning; folders carry files. |
| **Opportunistic Separation** | `trunk/opportunistic_separation.md` | Stand up projects the moment separation signals crystallize. Cost ≈ 0. |

## How the Ecology Grows

1. **Projects appear** when separation signals crystallize — different toolchain, lifecycle, failure modes. Each gets its own directory and governing document.
2. **The schema fills** as the graph encounters new node types and relations. `kernel/schema.md` accretes from what exists, not what was planned.
3. **Procedural memory deepens** as friction produces Graveyard and Gold entries.
4. **The omnibus grows** as tags accumulate, revealing patterns and strange attractors.
5. **Trunk protocols evolve** as friction reveals improvements worth sharing across branches.

Each branch is a holographic emanation of the kernel — it projects the full structural logic into its domain at the resolution that domain requires.

## The Hybrid Codex Pattern

Every significant document follows this structure:

- **Zone 1 — Routing Header**: What this is, what scope it governs, where to jump.
- **Zone 2 — Human Profile**: Meaning layer. Philosophy, vision, intent, locked decisions. Natural language.
- **Zone 3 — Machine Profile**: Execution layer. Paths, patterns, versions, hard rules, syntax.

A single document holds both. No parallel documentation.

## Kernel+ Self-Maintenance

This repo IS the kernel. It maintains itself through a deterministic packaging loop that any agent can run.

### The `#kernel+` Tag

During any FADE work anywhere in the ecology, atoms that appear domain-independent self-identify with a `#kernel+` tag in place. They don't move — they mark themselves as kernel-grade material where they were discovered.

### The Packaging Loop

1. **Harvest**: Walk the ecology, collect all `#kernel+` tagged atoms.
2. **Reflect**: Apply the veil of ignorance test to each candidate. Does it survive stripping of all domain-specific context? Would it be useful to a different human building a different ecology?
3. **Integrate**: Atoms that pass get absorbed into kernel/ or trunk/ documents, or become new documents if they represent genuinely new positions.
4. **Version**: `git add`, `git commit` with a message describing what was absorbed and from where.
5. **Push**: `git push` to the remote.

### The Veil of Ignorance Test

A pattern passes the veil if:
1. It makes sense without reference to any specific domain, project, or person
2. It would be useful to a different human building a different ecology
3. It describes structural logic, not domain content
4. Any existing fork could use it without modification

### Kernel+Extensions Packaging

The veil of ignorance is tunable. Pure kernel (kernel+0) applies maximum opacity — only domain-independent structure survives. But when packaging for a specific audience, the veil becomes translucent in declared dimensions:

- Describe the target: "this is for a musician" or "this is for a game developer"
- The omnibus tag substrate provides the vocabulary for matching
- Domain-specific atoms tagged `#kernel+` that also match the declared dimensions get included
- The packaging procedure is identical; only the attenuation changes

This produces a kernel+extensions economy: kernel+music, kernel+gamedev, kernel+whatever. Each is forking-ready because the packaging process guarantees structural soundness.

## Bootstrapping a New Ecology

If you've forked or cloned this repo, here's how to start:

### 1. Claim the Alpha Entity
Edit `alpha_entity.md`. Replace `[Your name]` and `[you]` with your actual identity. This is the zero-point — everything else relates to this node.

### 2. Read the Kernel
Read `kernel/node.md`, `kernel/relation.md`, `kernel/provenance.md` in that order. Then `kernel/node_schema.md` for how they compose. These are short and written in plain language. They ARE the structural commitments.

### 3. Read the Trunk
Read the protocols in `trunk/`. These are your operational tools. FADE is the most immediately useful — it's how anything enters the ecology. Opportunistic Separation tells you when to create new project directories. The Omnibus tells you how tags work.

### 4. Start Working
The ecology grows from your friction, not from planning. Start a project. FADE something. The schema will fill itself. Procedural memory will accrete from your mistakes and wins. Tags will emerge from your vocabulary.

### 5. Maintain the Kernel
As you work, tag domain-independent insights with `#kernel+`. Periodically run the packaging loop (harvest, reflect, integrate, version, push). The kernel evolves as you do.

## Git Operations

This repo uses a file-based commit message pattern for cross-platform compatibility:

```
# Write message to temp file
echo "kernel v[N]: [what was absorbed]" > .git/COMMIT_MSG
# Commit using the file
git commit -F .git/COMMIT_MSG
# Push
git push origin main
```

This avoids shell quoting issues across cmd.exe, PowerShell, and bash.

## What This Is Not

- Not a rigid framework. The protocols evolved from friction. They continue evolving.
- Not documentation for its own sake. Every file exists because the ecology needs it.
- Not someone else's system. The kernel provides structural logic. You provide the vitality, direction, and judgment. The ecology becomes yours through use.

## Provenance

Distilled from a tested ecology through a veil of ignorance process, 2026. The structural patterns emerged from real operational friction across multiple unrelated domains. Domain content was stripped. What remains is what generalizes.
