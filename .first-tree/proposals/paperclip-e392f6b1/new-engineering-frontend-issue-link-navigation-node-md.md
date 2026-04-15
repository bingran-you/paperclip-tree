---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR includes commits specifically for speeding up issue-to-issue navigation, resetting scroll position, and fixing prefetch typing — frontend navigation UX for issue links that no existing node covers (the drift issue-links node covers the data model, not frontend navigation performance).
---
# Issue Link Navigation

Frontend navigation performance and UX when traversing between linked issues — ensuring agents and humans can quickly follow issue-to-issue links without lag or stale state.

## Key Decisions

### Prefetch on Hover

When a user hovers over an issue link (via `IssueLinkQuicklook`), the target issue's data is prefetched so that navigation feels instant. This reduces perceived latency when agents or humans are following dependency chains across many linked issues.

### Scroll Reset on Navigation

When navigating from one issue detail view to another via an issue link, the scroll position resets to the top of the new issue. This prevents the disorienting experience of landing mid-page on a new issue after clicking a link.

**Rationale:** Agents traversing issue chains need to start reading from the top of each issue. Preserving scroll position across issue-to-issue navigation would force agents to scroll up, adding unnecessary steps to their workflow.

Source: PR "feat: polish inbox and issue list workflows" — commits "Speed up issue-to-issue navigation", "Reset scroll on issue detail navigation"
