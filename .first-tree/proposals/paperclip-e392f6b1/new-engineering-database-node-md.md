---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: PR adds migration 0056 introducing new sidebar preference tables (user_sidebar_preferences, company_user_sidebar_preferences) — the database node should list these in its schema overview.
---
Under the **Schema Organization** section, add to the relevant category:

- `user_sidebar_preferences` — Global per-user sidebar layout and display preferences
- `company_user_sidebar_preferences` — Company-scoped overrides for sidebar preferences

These tables were introduced in migration `0056_spooky_ultragirl.sql`.
