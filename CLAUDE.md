# CLAUDE.md — Meta-Agent Project Rules

## Project Identity

Meta-agent designs applied agents using FPF structures and evidence discipline.
It operates on descriptions (design-time), not domain expertise (run-time).

## Mandatory Skill

FPF skill (`/fpf`) is required for ALL work inside this project.
Every task must follow the FPF workflow: DECOMPOSE → EXECUTE → AUDIT.

## Core FPF Rules (Always Enforce)

### A.7 — Strict Distinction
- Object != Description != Carrier
- Role != Work
- MethodDescription != Method != Work
- **Capability != Method**: Capability = "can do X within WorkScope at WorkMeasures" (A.2.2). Method = "how to do X" (A.3). Never mix them.
- **Plan != Execution**: MethodDescription lives in design-time. Work lives in run-time and is immutable.

### A.10 — Evidence Graph
- Every claim that affects capabilities must have an Evidence reference.
- Evidence records are Epistemes bearing EvidenceRole (A.2.4).
- Evidence chains must be traceable: Claim → Evidence → Source.
- No orphan claims (claims without evidence links).

### B.3 / B.3.4 — Trust Calculus & Evidence Decay
- Every evidence record must have F-G-R scores (at least provisional).
  - F = Formality (how rigorous)
  - G = ClaimScope/Granularity (how broad)
  - R = Reliability (how trustworthy)
- Evidence decays over time. Declare DecayWindow for all evidence.
- "TBD" is acceptable only at initial creation; must be filled before status upgrades.

### A.2.1 — RoleAssignment
- Roles must be declared as Holder#Role:Context triples.
- Three defined roles: AgentDesigner, EvidenceAuditor, HumanApprover.

### A.15 — Role-Method-Work Alignment
- Every step in a method must reference which Role performs it.
- Work records must have: date, role, resources consumed, inputs/outputs.

## Boundary Rules (A.6.B)

- **No applied-domain knowledge** inside meta-agent artifacts.
- Applied content lives ONLY in applied agent folders or as test data in experiments/hypotheses.
- Applied agent naming requires explicit HumanApprover approval.
- When referencing applied-agent evidence (e.g., strategator/evidence/ST.EV-001), always prefix with the applied agent context to avoid naming collisions.

## Change Control (DRR per E.9)

- `changes/decision-log.md` follows canonical DRR format (E.9:4).
- Each DRR record must have: **ID**, Date, **Problem frame**, **Decision**, **Rationale** (with Pillar refs), **Consequences** (with impact list), Evidence/Refs, Status.
- Lightweight variant (CC-DRR.5): for non-semantic edits, Problem frame + Decision only with note "no semantic change".
- Statuses: provisional → accepted → revised.
- Capabilities remain provisional until evidence-backed.
- Capability status upgrades require evidence audit pass (at least smoke-level).

## Capability Schema (A.2.2 alignment)

When defining capabilities, use A.2.2 conceptual descriptors:

1. **CapabilityId** — unique identifier
2. **Holder** — which U.System has this capability
3. **Context** — U.BoundedContext where measures were established
4. **TaskFamily** — reference to MethodDescription(s) the system can execute
5. **WorkScope** — conditions/assumptions (USM ContextSlice, not free text)
6. **WorkMeasures** — CHR-style measurable targets
7. **QualificationWindow** — time policy for operational admissibility
8. **Evidence** — links to evidence records (A.10)
9. **F-G-R** — trust scores (B.3)
10. **DecayWindow** — evidence freshness window (B.3.4)
11. **Status** — provisional / smoke-validated / validated

Do NOT put Inputs/Outputs/Preconditions/Postconditions here — those belong in MethodDescriptions (method/ files).

## Hypothesis-Experiment-Evidence Chain

- Hypothesis → Experiment → Evidence → Capability upgrade
- When an experiment completes, update the linked hypothesis status.
- Evidence naming must include context prefix to avoid cross-context collisions:
  - Meta-agent evidence: `MA.EV-NNN`
  - Applied agent evidence: `ST.EV-NNN` (Strategator), etc.

## Directory Structure

```
bounded-context/    Context scope, entities, distinctions
capabilities/       Meta-agent capabilities (A.2.2 schema)
hypotheses/         Hypotheses about agent creation process
experiments/        Experiment records (Work per A.15.1)
sources/            Evidence templates and meta-agent sources
changes/            Decision log (DRR per E.9)
method/             MethodDescriptions (design-time recipes)
```

## Workflow for Any Task

1. Invoke `/fpf` skill
2. Detect language (ISO 639-1)
3. Map request to FPF concepts (Holon, BoundedContext, Method vs Work)
4. Navigate to relevant FPF domain (foundations/transformation/trust-evidence/reasoning/aggregation)
5. Execute with strict A.7 discipline
6. Update evidence graph (A.10) and DRR (E.9) if structural change
7. Verify all claims have evidence references before marking complete

## Git Commit Rules

### Commit granularity
- **One commit per DRR** (or per logical unit of work if no DRR applies).
- A DRR that touches multiple files gets ONE commit with all affected files.
- Non-semantic edits (CC-DRR.5) may be batched into a single "housekeeping" commit.

### Commit message format
```
<type>(<scope>): <short summary>

<body — what changed and why, reference DRR-ID>

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>
```

**Types**: `feat` (new capability/method/structure), `fix` (correction), `refactor` (restructure without semantic change), `docs` (documentation-only), `chore` (housekeeping, tooling).

**Scope**: affected area — `capabilities`, `method`, `evidence`, `bounded-context`, `changes`, `experiments`, `hypotheses`, or `meta` (cross-cutting).

### Rules
- Always reference DRR-ID in commit body when a DRR exists for the change.
- Commit message language: English (project artifacts may be bilingual, but git log stays English).
- Do NOT commit partial DRR work — a DRR's changes must be atomic.
- Do NOT amend published commits unless explicitly asked.
- Stage specific files by name, not `git add -A` or `git add .`.

## Anti-Patterns (Do NOT)

- Do NOT confuse Capability with Method (Capability = can do; Method = how to do)
- Do NOT leave F-G-R as "TBD" when upgrading capability status
- Do NOT reference applied-domain evidence without context prefix
- Do NOT update capability status without experiment evidence
- Do NOT create hypotheses without evidence plan
- Do NOT skip DRR entry on structural changes
- Do NOT use "DRR-lite" — use canonical DRR (E.9) or CC-DRR.5 lightweight variant
