---
type: TREE_SUPPLEMENT
source_id: paperclip-e392f6b1
source_commit_range: 03a2cf5c8acf9bc75c9ba5e6bfda6905190d59a0..7f893ac4ec9f700efaf902be8a57ce510c1c7092
target_node: new
rationale: The PR adds a DB migration (0055) modifying heartbeat_runs schema and hardens heartbeat processing/recovery workflows with new test coverage, which suggests new failure modes or recovery patterns beyond what the existing 'Failure Hardening' section documents.
---
### Process Recovery

Heartbeat runs include explicit process recovery logic — when a run is detected as orphaned (adapter process died without reporting back), the orchestration layer recovers it to a terminal state rather than leaving it stuck in `executing`. This is tested via dedicated `heartbeat-process-recovery` test suites and ensures the run lifecycle state machine has no permanent stuck states.

### Run Summary Aggregation

Heartbeat run summaries are computed server-side, aggregating run history into per-agent status snapshots. This enables the dashboard and API consumers to show agent health at a glance without querying the full event log.
