---
type: TREE_MISS
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR modifies Sidebar, SidebarAgents, SidebarNavItem, and SidebarProjects — sidebar navigation structure and preferences with no existing tree node covering this area.
---
# Sidebar & Navigation

Layout and navigation patterns for the application sidebar — the persistent navigation surface that provides access to agents, projects, and top-level views.

## Key Decisions

### Sidebar Sections for Domain Entities

The sidebar is organized into discrete sections for agents (`SidebarAgents`) and projects (`SidebarProjects`), each with their own rendering and collapse behavior. Navigation items (`SidebarNavItem`) follow a consistent pattern across sections.

### Layout Integration

The sidebar is managed as part of the top-level `Layout` component, ensuring consistent positioning and responsive behavior across all pages.

Source: PR "feat: polish inbox and issue list workflows"
