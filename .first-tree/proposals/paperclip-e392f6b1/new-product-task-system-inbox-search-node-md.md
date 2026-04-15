---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: PR improves issue search matching logic on both server (issues service) and client (inbox lib), which supplements the existing inbox search node's coverage of how search matches work.
---
### Improved Issue Search Matches

Search matching was improved to return more relevant results when searching for issues in the inbox. Changes span both server-side matching (in the issues service) and client-side filtering (in the inbox library), ensuring that improved matching applies consistently whether results come from the server or are filtered locally.

### Command Palette Search Integration

The command palette (`CommandPalette.tsx`) uses the same improved search matching logic as the inbox, ensuring consistent search behavior across both the inbox view and the command palette. This is a shared concern — changes to search matching should be validated in both surfaces.
