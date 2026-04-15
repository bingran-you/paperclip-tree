---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR adds DEVELOPING.md, a memory-landscape doc, and a memory-service API plan — developer documentation and architectural planning docs that no existing tree node covers.
---
# Developer Documentation

Developer-facing documentation that lives outside the source code: onboarding guides, architectural landscape docs, and design plans.

## Key Decisions

### Centralized Doc Directory

Long-form developer documentation lives in `doc/` at the repo root rather than scattered across packages. This includes the contributor guide (`DEVELOPING.md`), architectural landscape documents, and time-bound design plans (`doc/plans/`).

### Memory Service Landscape

A `memory-landscape.md` document captures the current state and planned evolution of agent memory — how agents persist and retrieve context across sessions. An accompanying plan (`doc/plans/2026-03-17-memory-service-surface-api.md`) defines the API surface for the memory service.

**Rationale:** Memory is a cross-cutting concern that touches adapters, the backend, and the product layer. A standalone landscape doc prevents this context from being fragmented across domain-specific nodes.
