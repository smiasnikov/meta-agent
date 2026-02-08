# Capabilities: Meta-Agent (Level 1 — Provisional)

All capabilities are provisional and must be validated by evidence (A.10 / B.3 / B.3.4).

## Level 1 schema (A.2.2 alignment)

Fields per U.Capability (A.2.2 conceptual descriptors):
- **CapabilityId** — unique identifier
- **Description** — what the system can do (positive, measurable terms)
- **Holder** — which U.System has this capability
- **Context** — U.BoundedContext where measures are established (A.1.1)
- **TaskFamily** — reference to MethodDescription(s) the system can execute (A.3.2)
- **WorkScope** — conditions/assumptions under which capability holds (A.2.6 USM)
- **WorkMeasures** — measurable targets (CHR-style, A.17)
- **Evidence** — links to evidence records (A.10)
- **F-G-R** — trust scores: Formality, ClaimScope, Reliability (B.3)
- **DecayWindow** — evidence freshness window (B.3.4)
- **Status** — provisional / smoke-validated / validated

Note: Inputs, Outputs, Preconditions, Postconditions belong in MethodDescriptions (method/ files), NOT in capability declarations (A.7 Strict Distinction: Capability ≠ Method).

## Capability table

| CapabilityId | Description | Holder | Context | TaskFamily | WorkScope | WorkMeasures | Evidence | F-G-R | DecayWindow | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| MA.CAP.01 | Extract requirements from agent descriptions | MetaAgent | meta-agent | [method/02](../method/02-requirement-extraction.md) | Any domain; text-only input | Requirements list produced; completeness ≥ 80% | TBD | F1/G:meta-agent/R:low | 6 months | provisional |
| MA.CAP.02 | Derive U.Capability + scope for applied agents | MetaAgent | meta-agent | [method/03](../method/03-capability-derivation.md) | Any domain; structured requirements input | Capability list with WorkScope per item | TBD | F1/G:meta-agent/R:low | 6 months | provisional |
| MA.CAP.03 | Produce MethodDescriptions and Work templates | MetaAgent | meta-agent | [method/04](../method/04-template-production.md) | FPF-only; capability list input | Templates created; FPF-conformant | TBD | F1/G:meta-agent/R:low | 6 months | provisional |
| MA.CAP.04 | Design evidence scheme and validation workflow | MetaAgent | meta-agent | [method/05](../method/05-evidence-design.md) | FPF-only; capabilities input | Evidence schema with F-G-R slots | TBD | F1/G:meta-agent/R:low | 6 months | provisional |
| MA.CAP.05 | Define KB and dataset schemas (domain-agnostic) | MetaAgent | meta-agent | [method/06](../method/06-schema-design.md) | FPF-only; capabilities input | Schema created; domain-agnostic | TBD | F1/G:meta-agent/R:low | 6 months | provisional |
| MA.CAP.06 | Map domain sources into FPF slots | MetaAgent | meta-agent | [method/07](../method/07-source-mapping.md) | Structure-only; source list input | Mappings created; ≥ 80% sources mapped | TBD | F1/G:meta-agent/R:low | 6 months | provisional |
| MA.CAP.07 | Perform evidence audit of applied capabilities | MetaAgent | meta-agent | [method/08](../method/08-evidence-audit.md) | FPF-only; capability table + evidence records | Audit report with pass/fail per capability | EXP-001 (Strategator: 10/10 pass) | F1/G:meta-agent/R:smoke | 6 months | smoke-validated |

## Roadmap (future formalization)
- **Level 2** (partially done): TaskFamily now links to actual MethodDescription files. Remaining: add RoleAssignment (A.2.1) per capability.
- **Level 3**: represent capabilities as U.Capability objects with EvidenceGraph IDs and formal WorkMeasures (A.17/A.18 CSLC).

## Notes
- No applied-domain knowledge in this file.
- MA.CAP.07 upgraded to smoke-validated based on EXP-001 evidence audit (DRR-005).

## References
- BoundedContext → ../bounded-context/00-index.md
- U.Capability pattern → A.2.2
- Decision: DRR-001 (Level 1 formalization), DRR-005 (evidence audit requirement)
