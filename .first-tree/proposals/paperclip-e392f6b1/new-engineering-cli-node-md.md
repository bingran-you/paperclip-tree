---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The CLI node lists commands but doesn't mention that onboard, configure, and run now integrate bind preset selection, or that a new deployment-auth health check was added to the doctor checks.
---
Under **Instance Management**, the `onboard`, `configure`, and `run` commands now include bind preset selection for network binding configuration. Under **Adapter & Check Integration**, a `deployment-auth-check` was added to validate bind preset and auth mode compatibility.
