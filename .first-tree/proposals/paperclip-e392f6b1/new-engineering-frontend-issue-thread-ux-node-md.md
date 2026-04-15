---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR adds activity formatting (activity-format.ts) and markdown editor improvements (MarkdownEditor.tsx) that extend the existing thread UX node's coverage of rendering patterns.
---
### Activity Formatting

Thread activity entries (status changes, assignment updates, field modifications) are formatted via a dedicated transform layer (`activity-format.ts`) that produces consistent, human-readable activity summaries. This ensures both agent-triggered and human-triggered activities display uniformly in the thread.

### Markdown Editor Improvements

The markdown editor used for composing thread replies received UX improvements as part of PR #3678, enhancing the authoring experience for both agents and humans within the thread view.
