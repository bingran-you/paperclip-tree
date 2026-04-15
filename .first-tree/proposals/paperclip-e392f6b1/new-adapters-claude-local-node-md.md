---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR modifies prompt-cache.ts and skills.ts in the Claude local adapter — prompt caching is a capability not mentioned in the existing node, and the changes suggest hardening of how cached prompts and skill injection interact with execution.
---
### Prompt Caching

The Claude local adapter implements prompt caching (`prompt-cache.ts`) to avoid re-sending identical system prompts and skill content across consecutive heartbeat runs. This reduces token usage and latency for agents that run frequently with stable configurations. The cache is invalidated when skills or agent instructions change.
