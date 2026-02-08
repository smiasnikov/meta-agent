# Decision Log (DRR per E.9)

## Format (E.9:4)

Each record contains four mandatory components:

- **ID**: unique identifier (DRR-NNN)
- **Date**: decision date
- **Problem frame**: why are we talking about this?
- **Decision**: what will we do? (normative text)
- **Rationale**: why is this the right thing? (Pillar/Taxonomy refs)
- **Consequences**: what happens next? (impact, trade-offs, affected artifacts)
- **Evidence/Refs**: supporting evidence
- **Status**: provisional / accepted / revised

Lightweight variant (CC-DRR.5): for non-semantic edits (typos, wording), Problem frame + Decision only, with note "no semantic change".

---

## DRR-001

**Date**: 2026-02-01
**Problem frame**: Meta-agent needs a capability formalization level to start work. Full U.Capability (A.2.2) requires WorkScope, WorkMeasures, QualificationWindow — too heavy for bootstrapping.
**Decision**: Use Level 1 capability formalization (table with fields) and document Level 2/3 as roadmap.
**Rationale**: Start minimal but FPF-consistent (P-1 Cognitive Elegance, P-10 Open-Ended Evolution); allow iterative refinement. Pillar check: P-7 Pragmatic Utility — a provisional table is immediately useful.
**Consequences**: Capability table is provisional until evidence-backed. Level 2/3 formalization deferred. Affected: capabilities/meta-agent.md.
**Evidence/Refs**: Human-in-the-loop feedback (session 2026-02-01).
**Status**: accepted

---

## DRR-002

**Date**: 2026-02-01
**Problem frame**: Risk of applied-domain knowledge leaking into meta-agent artifacts, violating A.7 Strict Distinction. Without explicit boundary, meta-agent descriptions will mix with applied content.
**Decision**: Meta-agent is domain-agnostic; applied knowledge only in applied agent folders or in experiments/hypotheses as test data.
**Rationale**: Enforce A.7 boundary (Object ≠ Description); A.6.B Boundary Norms. Pillar check: P-3 Cross-Scale Consistency — boundary rule must hold at all levels.
**Consequences**: All applied-domain files must live outside meta-agent context. Experiments may reference applied agents as test cases only. Affected: bounded-context/01-scope.md, bounded-context/03-distinctions.md, all future artifacts.
**Evidence/Refs**: Human-in-the-loop feedback (session 2026-02-01).
**Status**: accepted

---

## DRR-003

**Date**: 2026-02-01
**Problem frame**: Agent naming is a contextual decision with semantic weight. Automated naming without human review risks misleading names and unclear boundaries.
**Decision**: Applied agent naming requires explicit human approval (HumanApprover role).
**Rationale**: Boundary constraint (A.6.B). Pillar check: P-2 Didactic Primacy — names must be clear; P-6 Human-Centric — human judgement for semantic choices.
**Consequences**: New role HumanApprover required. All applied agent creation workflows must include naming approval step. Affected: bounded-context/02-entities.md, method/01-agentic-workflow.md.
**Evidence/Refs**: Human-in-the-loop feedback (session 2026-02-01).
**Status**: accepted

---

## DRR-004

**Date**: 2026-02-01
**Problem frame**: Course materials for Strategator were mixed with evidence records. Sources (carriers) and Evidence (claims) must be separated per A.7 and A.10.
**Decision**: Move applied course materials under strategator/sources/ and separate Evidence records in strategator/evidence/.
**Rationale**: Sources are Carriers (A.7); Evidence are Epistemes bearing EvidenceRole (A.2.4) with traceability (A.10). Pillar check: P-4 Ontological Parsimony — separate only what is semantically distinct.
**Consequences**: Strategator directory restructured. Evidence records (ST.EV-001..004) now separate from source carriers. Affected: strategator/sources/, strategator/evidence/.
**Evidence/Refs**: Human-in-the-loop feedback (session 2026-02-01).
**Status**: accepted

---

## DRR-005

**Date**: 2026-02-01
**Problem frame**: Without mandatory evidence audit in experiments, capability status upgrades are unjustified claims.
**Decision**: Evidence audit is a standard experiment step; capability status upgrades require at least smoke-level audit.
**Rationale**: Enforce A.10/B.3 traceability. Pillar check: P-8 Evidence-Based — every claim needs warrant; P-10 Open-Ended Evolution — audit enables iterative confidence building.
**Consequences**: All experiments must include evidence audit section. Capability status progression: provisional → smoke-validated → validated. Affected: experiments/, capabilities/meta-agent.md, AGENTS.md.
**Evidence/Refs**: Human-in-the-loop feedback (session 2026-02-01).
**Status**: accepted

---

## DRR-006

**Date**: 2026-02-07
**Problem frame**: Decision log used "DRR-lite" — a non-canonical format missing Problem frame, Consequences, and decision IDs per E.9. This undermines auditability (CC-DRR.1) and makes rationale incomplete (CC-DRR.2).
**Decision**: Upgrade decision log to canonical DRR format (E.9:4) with all four components: Problem frame, Decision, Rationale, Consequences. Add unique IDs. Remove all "DRR-lite" references across project.
**Rationale**: Align with E.9 conformance checklist (CC-DRR.1 through CC-DRR.5). Pillar check: P-10 Open-Ended Evolution — structured rationale prevents conceptual erosion; P-2 Didactic Primacy — full DRR is more learnable than ad-hoc format; P-1 Cognitive Elegance — one canonical format, not a variant.
**Consequences**: All 5 existing entries retroactively expanded with Problem frame and Consequences. All project references updated from "DRR-lite" to "DRR (E.9)". CC-DRR.5 lightweight variant available for trivial edits. Affected: changes/decision-log.md, AGENTS.md, CLAUDE.md, README.md, method/01-agentic-workflow.md.
**Evidence/Refs**: FPF pattern E.9 (Design-Rationale Record); gap analysis in review session 2026-02-07.
**Status**: accepted

---

## DRR-007

**Date**: 2026-02-07
**Problem frame**: Capability table references 7 TaskFamily MethodDescriptions (method/02..08) that do not exist. These are broken links violating A.10 traceability. Without actual MethodDescriptions, meta-agent capabilities are claims without executable recipes (A.3.2).
**Decision**: Create 7 MethodDescription files (method/02 through method/08) following A.3.2:4.3 structure. Each file covers: Purpose, Interface, Preconditions, Postconditions, Role requirements, Capability thresholds, Failure semantics, Steps. Update capability table TaskFamily links to point to actual files.
**Rationale**: A.3.2 requires MethodDescriptions to be explicit epistemic artifacts. A.15 Role-Method-Work alignment requires each capability's TaskFamily to reference an actual recipe. Pillar check: P-8 Evidence-Based — executable recipes make capabilities testable; P-7 Pragmatic Utility — MethodDescriptions enable reuse across applied agents.
**Consequences**: 7 new files in method/. Capability table TaskFamily links updated from "(TBD)" to actual file references. Level 2 roadmap partially fulfilled (TaskFamily linking done; RoleAssignment per capability still pending). Affected: method/, capabilities/meta-agent.md.
**Evidence/Refs**: FPF pattern A.3.2 (U.MethodDescription); capability table gap analysis 2026-02-07.
**Status**: accepted

---

## DRR-008

**Date**: 2026-02-08
**Problem frame**: Strategator (first applied agent) was created before meta-agent structural review and contained multiple FPF violations: capability table had Inputs/Outputs (A.7 violation); no bounded-context, MethodDescriptions, or decision log; evidence files lacked ST. prefix (collision risk). Structure was not isomorphic to meta-agent pattern.
**Decision**: Validate and align Strategator structure with meta-agent pattern. Rebuild capabilities table to A.2.2 schema. Create bounded-context/ (4 files), method/ (10 MethodDescriptions), changes/decision-log.md, CLAUDE.md. Rename evidence files with ST. prefix. Update all cross-references.
**Rationale**: Applied agents must follow the same structural patterns as meta-agent (P-3 Cross-Scale Consistency). A.2.2 schema requires Holder, Context, TaskFamily, WorkScope, WorkMeasures — not Inputs/Outputs. A.3.2 requires MethodDescriptions for each TaskFamily. A.10 requires evidence traceability with context prefixes. Pillar check: P-8 Evidence-Based — structural alignment enables formal testing; P-10 Open-Ended Evolution — consistent structure across agents enables reuse of meta-agent methods.
**Consequences**: Strategator now structurally isomorphic to meta-agent. 10 MethodDescriptions created (method/01..10). Capabilities table rebuilt with 11-field A.2.2 schema. Evidence renamed ST.EV-001..004. Decision log with ST.DRR-001..002 created. CLAUDE.md operational rules added. Ready for EXP-002 capability testing. Affected: all files in ../strategator/.
**Evidence/Refs**: Structural audit 2026-02-08; FPF patterns A.2.2, A.3.2, A.7, A.10; meta-agent as reference pattern.
**Status**: accepted
