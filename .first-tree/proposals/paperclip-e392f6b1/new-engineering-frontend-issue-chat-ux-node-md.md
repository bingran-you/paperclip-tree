---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR introduces a chat-based conversation UX for issues (IssueChatThread, issue-chat-messages, issue-chat-scroll) using @assistant-ui/react, which is a distinct UX paradigm from the existing comment-thread rendering covered by engineering/frontend/issue-thread-ux.
---
# Issue Chat UX

Chat-style conversation interface for issue threads — renders issue comments as a real-time chat experience using `@assistant-ui/react` components, distinct from the traditional comment-thread rendering.

## Key Decisions

### Chat-Over-Comments Paradigm

Issue comments render as a bottom-up chat conversation rather than a traditional forum-style comment list. This matches the rapid back-and-forth between agents and humans, where issue threads function more like a messaging channel than a discussion board. The chat UX supports streaming responses and markdown rendering optimized for verbose agent output (plans, diffs, status reports).

### Dedicated Message Transform Layer

Raw issue comments are transformed into chat messages via `issue-chat-messages.ts` before rendering. This layer normalizes agent-generated and human-generated comments into a uniform chat message format, handling differences in structure, metadata, and content type.

### Scroll Management

Chat scroll behavior is managed by a dedicated module (`issue-chat-scroll.ts`) that handles auto-scroll-to-bottom for new messages, scroll position preservation during history loading, and scroll-to-bottom button offset when the properties panel is open.

Source: PR #3678 (`[codex] Improve issue detail and issue-list UX`)
