---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The existing bind-presets node captures the concept and two key decisions but doesn't document the actual preset names, the CLI integration surface (onboard/configure/run commands all consume presets), or that the implementation lives in both packages/shared/src/network-bind.ts and cli/src/config/server-bind.ts.
---
### CLI Integration

Bind presets are wired into all three primary CLI commands that manage the server: `onboard`, `configure`, and `run`. The onboard wizard prompts for a bind preset during first-time setup; `configure` allows changing it later; `run` resolves the selected preset into concrete host/port bindings at startup. The preset selection is persisted in the instance config via `packages/shared/src/config-schema.ts`.

### Shared Network-Bind Module

Preset resolution logic lives in `packages/shared/src/network-bind.ts`, making it available to both the CLI and the server. This avoids duplicating binding logic across packages.

### Deployment Auth Check

A new health check (`cli/src/checks/deployment-auth-check.ts`) validates that the chosen bind preset is compatible with the deployment's authentication mode — e.g., flagging if a `public` preset is used without authentication enabled.
