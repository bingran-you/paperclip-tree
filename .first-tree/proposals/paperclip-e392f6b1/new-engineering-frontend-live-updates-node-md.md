---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR introduces a LiveUpdatesProvider context (LiveUpdatesProvider.tsx) for real-time issue updates — a cross-cutting frontend infrastructure concern not covered by any existing node.
---
# Live Updates

Real-time update infrastructure for keeping issue-related UI surfaces current as agents and humans make changes.

## Key Decisions

### React Context Provider Pattern

Live updates are delivered via a React context provider (`LiveUpdatesProvider`) that wraps issue-related views. This integrates with React Query's cache invalidation rather than introducing a separate synchronization layer, keeping the architecture aligned with the existing data-fetching patterns.

### Optimized for Agent Activity

The live update system is designed to handle the high-frequency mutations typical of autonomous agent activity — rapid status transitions, comment bursts, and concurrent field updates — without overwhelming the UI with refetches.

Source: PR #3678 (`[codex] Improve issue detail and issue-list UX`)
