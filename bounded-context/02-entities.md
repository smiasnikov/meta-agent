# Core Entities and Roles (Meta-Agent)

## Core entities (A.1)
- U.System: **MetaAgent** — the system that designs applied agents
- U.System: **AppliedAgent** (placeholder only, no domain content here)

## Core roles (A.2)
- U.Role: **AgentDesigner** — designs applied agent structures
- U.Role: **EvidenceAuditor** — validates evidence chains and F-G-R
- U.Role: **HumanApprover** — approves applied agent naming (DRR-003)

## Role assignments (A.2.1)

| Holder | Role | Context | Notes |
|--------|------|---------|-------|
| MetaAgent | AgentDesigner | meta-agent | Primary design role |
| MetaAgent | EvidenceAuditor | meta-agent | Audit role; may also be held by human |
| Human | HumanApprover | meta-agent | Naming approval; cannot be delegated to MetaAgent |

## Core artifact types (A.7 classification)

**Design-time artifacts (Descriptions):**
- U.MethodDescription — design-time recipes (method/ files)

**Run-time artifacts (Work):**
- U.Work — execution records (experiments/ files)

**Dispositional properties (not artifacts):**
- U.Capability — ability of a System within WorkScope at WorkMeasures (A.2.2). Declared in capabilities/ files. NOT an artifact — a property of a System.

**Epistemic artifacts:**
- U.Episteme bearing U.EvidenceRole (A.2.4) — evidence items with F-G-R and traceability (sources/ and applied-agent evidence/ files)

## Notes
- AppliedAgent is referenced only as a **type placeholder**.
- All applied-domain details live outside meta-agent context (DRR-002).
- U.Capability is a dispositional property, not an artifact or role (A.2.2:4.1, A.7).

## References
- Scope → [01-scope.md](01-scope.md)
- Distinctions → [03-distinctions.md](03-distinctions.md)
- Capability pattern → A.2.2
- EvidenceRole pattern → A.2.4
