---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR adds a SECURITY.md vulnerability disclosure policy and a security advisory handling skill — the existing security node covers hardening decisions but not the vulnerability reporting/disclosure process.
---
### Vulnerability Disclosure Policy

A `SECURITY.md` file defines the project's vulnerability reporting process. Security issues should be reported through the documented channel rather than public GitHub issues. A dedicated agent skill (`deal-with-security-advisory`) handles triage of incoming security advisories, ensuring they are assessed and routed consistently.

**Rationale:** As an open-source project, Paperclip needs a clear, public-facing process for responsible disclosure. The agent skill ensures advisory triage is not bottlenecked on a single human.
