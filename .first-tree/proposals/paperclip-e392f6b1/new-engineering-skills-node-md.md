---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR adds agent skills (paperclip-create-agent, paperclip, deal-with-security-advisory) in a top-level `skills/` directory — these are developer-authored agent skill definitions that no existing tree node covers.
---
# Agent Skills

Reusable skill definitions that agents can invoke during task execution. Skills live in `skills/` at the repo root and in `.agents/skills/`.

## Key Decisions

### Skills as Declarative Definitions

Each skill is a `SKILL.md` file with optional `references/` containing supporting material (e.g., API reference docs). Skills are declarative — they describe what the agent should do and provide context, rather than containing executable code.

### Current Skills

- **`paperclip`** — General Paperclip API interaction skill with API reference.
- **`paperclip-create-agent`** — Skill for creating new agents within a company, with API reference for the agent creation endpoints.
- **`deal-with-security-advisory`** — Skill for triaging and responding to security advisories.

### Separation from Plugins

Skills are distinct from plugins. Plugins extend the runtime with executable code (SDK, sandbox, lifecycle hooks). Skills are prompt-level context injected into agent sessions to guide behavior. They do not run code — they inform the agent's approach.
