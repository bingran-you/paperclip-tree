---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR introduces issue list rendering patterns (IssuesList, IssueRow, IssueColumns, KanbanBoard, IssueFiltersPopover) with no existing node covering issues list UX — distinct from the inbox list node which covers the inbox view.
---
# Issues List UX

Rendering, filtering, and interaction patterns for the issues list view — the primary surface where agents and humans browse, triage, and manage work items across a project.

## Key Decisions

### Unified List and Kanban Rendering

The issues list supports both a table/list view (`IssuesList`, `IssueRow`, `IssueColumns`) and a kanban board view (`KanbanBoard`). Both share the same data source and filtering logic, with the rendering mode toggled by the user. This avoids duplicating data-fetching and filter state across two separate implementations.

### Client-Side Filtering via Popover

Issue filters are applied client-side through a filter popover (`IssueFiltersPopover`) that operates on the already-loaded dataset. This is consistent with the inbox list's skip-refetch-on-filter pattern and keeps the list responsive during rapid triage.

### Keyboard Navigation

The issues list integrates with a keyboard shortcuts system (`useKeyboardShortcuts`) that enables navigation, selection, and quick actions without mouse interaction. A cheatsheet overlay (`KeyboardShortcutsCheatsheet`) surfaces available shortcuts. This is critical for agent-like interaction patterns where keyboard-driven workflows are faster.

Source: PR "feat: polish inbox and issue list workflows"
