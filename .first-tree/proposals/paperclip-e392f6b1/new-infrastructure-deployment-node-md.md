---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The deployment node documents Docker architecture and environment variables but doesn't mention bind presets as a deployment configuration mechanism or link to the bind-presets child node.
---
### Bind Presets

Network binding is configured via named presets rather than raw host/port values. See [bind-presets/NODE.md](bind-presets/NODE.md) for details. Presets are selected during CLI onboard/configure and resolved at server startup.
