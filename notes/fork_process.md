# fork process

how this kernel was distilled, so the process itself is reproducible.

## the veil of ignorance test

take every document in a working ecology. for each one, ask:
does this make sense if you remove all references to specific
people, projects, tools, and domains?

what survives is kernel. what doesn't is domain content — valuable
in its home, but not structural.

## what was stripped

- all project-specific directories and content
- all person-specific identity details (names, handles, credentials)
- all tool-specific configurations and paths
- all domain vocabulary that wouldn't generalize
- all accumulated procedural memory (it's domain-specific by nature)

## what was kept

- the five foundational positions (node, relation, provenance,
  node_schema, schema) — these describe HOW any node works,
  not WHAT specific nodes exist
- the seven trunk protocols — these describe HOW to operate,
  not WHAT to operate on
- the alpha entity template — the structural role of the
  sovereign human, not any specific human
- the hybrid codex pattern — a document structure that holds
  human meaning and machine execution in one place

## the test for completeness

can someone fork this repo, fill in alpha_entity.md with their
own name, and start building an ecology that works? if yes,
the kernel is sufficient. if no, something structural was
accidentally stripped.

## the test for contamination

does anything in the kernel reference a specific person, project,
tool, or domain? if yes, either it's genuinely structural (and
should be abstracted) or it's domain content that leaked through
(and should be removed).

## provenance of this process

first performed 2026-04-20 to produce a fork for a specific user.
the fork passed both tests: the new user could bootstrap from it,
and zero dangling references to the source ecology remained.
documented here so any future fork can follow the same procedure.
