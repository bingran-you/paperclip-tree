---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR adds graceful handling of harness checkout conflicts and signoff e2e fixes for auto-checked-out issues — the existing node covers the happy path but not conflict resolution behavior.
---
### Graceful Conflict Handling

When the harness attempts auto-checkout and encounters a conflict (another agent already holds the issue), the checkout fails gracefully rather than crashing the agent's boot sequence. The agent proceeds without exclusive checkout and can be retried or reassigned.

**Rationale:** Hard failures on checkout conflicts during wake would block agents from booting entirely. Graceful handling allows the system to surface the conflict for resolution while keeping the agent operational.

Source: PR "feat: polish inbox and issue list workflows" — commit "Handle harness checkout conflicts gracefully"
