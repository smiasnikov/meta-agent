# Meta-Agent Rules (Operational)

## Mandatory skill
- **FPF skill is required** for all work inside meta-agent artifacts.

## Core FPF rules
- Enforce A.7: Object ≠ Description ≠ Carrier; Role ≠ Work; MethodDescription ≠ Work.
- Every claim that affects capabilities must have Evidence (A.10).
- Evidence must be stored as separate records with F-G-R + decay (B.3/B.3.4).

## Boundary rules (A.6.B)
- No applied-domain knowledge inside meta-agent artifacts.
- Applied content lives in applied agent folders or in meta-agent experiments/hypotheses as test data only.
- Applied agent naming requires explicit human approval (HumanApprover).

## Change control (E.9 DRR)
- Decision log is a DRR-lite (E.9) and must be updated on any structural change.
- Capabilities remain provisional until evidence-backed.

## Process
- Work in small steps, show file content before writing.
- Maintain linkage: Hypothesis → Experiment → Evidence → Capability.
