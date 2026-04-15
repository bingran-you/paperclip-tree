---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR introduces inline sub-issue rendering within the parent issue detail view (issue-detail-subissues.ts), a new UX pattern not covered by any existing node.
---
# Issue Detail Sub-Issues

Inline rendering of sub-issues within the parent issue detail view, keeping the full issue hierarchy visible without requiring separate navigation.

## Key Decisions

### Inline Sub-Issue Display

Sub-issues are displayed inline within the parent issue's detail view rather than in a separate tab or navigation target. This reduces navigation friction for agents and humans working through a task hierarchy, keeping parent context visible while reviewing child issues.

### Sub-Issue Data Module

Sub-issue rendering logic is extracted into a dedicated module (`issue-detail-subissues.ts`) that handles data shaping, ordering, and status aggregation for the inline display.

Source: PR #3678 (`[codex] Improve issue detail and issue-list UX`)
