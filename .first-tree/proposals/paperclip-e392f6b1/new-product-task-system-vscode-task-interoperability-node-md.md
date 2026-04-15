---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR includes a plan document (doc/plans/2026-04-12-vscode-task-interoperability-plan.md) for VSCode task interoperability — a new integration surface not covered by any existing node.
---
# VSCode Task Interoperability

Plan for integrating Paperclip's task system with VSCode's task runner, enabling developers to interact with Paperclip issues and agent work directly from their IDE.

## Status

Planning phase. A design plan has been drafted (see `doc/plans/2026-04-12-vscode-task-interoperability-plan.md` in source) but implementation has not begun.

## Context

This integration would allow VSCode users to view, assign, and track Paperclip issues without leaving the editor, bridging the gap between the Paperclip web UI and the developer's local workflow. The plan explores how Paperclip tasks map to VSCode's task provider API.

## Boundaries

- The task system domain model is owned by `product/task-system/NODE.md`.
- IDE-specific adapter behavior (e.g., Cursor) is owned by the respective adapter node.
