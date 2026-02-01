# Decision Log (DRR-lite)

## Format
- Date
- Decision
- Rationale
- Evidence/Refs
- Status (provisional/accepted/revised)

---

2026-02-01
Decision: Use Level 1 capability formalization (table with fields) and document Level 2/3 as roadmap.
Rationale: Start minimal but FPF-consistent; allow iterative refinement.
Evidence/Refs: Human-in-the-loop feedback (this session).
Status: accepted

2026-02-01
Decision: Meta-agent is domain-agnostic; applied knowledge only in applied agent folders or in experiments/hypotheses as test data.
Rationale: Enforce A.7 boundary; avoid leakage of applied knowledge into meta-agent.
Evidence/Refs: Human-in-the-loop feedback (this session).
Status: accepted

2026-02-01
Decision: Applied agent naming requires explicit human approval (HumanApprover role).
Rationale: Boundary constraint for naming decisions (A.6.B).
Evidence/Refs: Human-in-the-loop feedback (this session).
Status: accepted

2026-02-01
Decision: Move applied course materials under strategator/sources/ and separate Evidence records in strategator/evidence/.
Rationale: Keep Sources as carriers and Evidence as claims with traceability (A.10).
Evidence/Refs: Human-in-the-loop feedback (this session).
Status: accepted
