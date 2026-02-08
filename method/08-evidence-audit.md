# Evidence Audit (MethodDescription, A.3.2)

## Purpose
Describes the method for performing evidence audit of applied agent capabilities.
Linked capability: MA.CAP.07 (smoke-validated via EXP-001).

## Interface (inputs/outputs)
- **Inputs**: Capability table + evidence records + source list
- **Outputs**: Audit report (pass/fail per capability, aggregate F-G-R, gaps list)
- **Resources**: FPF skill, A.10, B.3, B.3.4

## Preconditions
- Capability table is populated with evidence links
- Evidence records exist with F-G-R values
- Sources are accessible for verification

## Postconditions / Effects
- Each capability has audit result: pass / fail / gap
- Aggregate F-G-R computed for the audit as a whole
- Gaps are explicit and actionable
- Capability status upgrade recommendations produced (if applicable, per DRR-005)

## Non-functional constraints
- Audit is structural: verifies evidence-to-capability traceability, not domain correctness
- Must not import applied-domain knowledge into meta-agent context (DRR-002)

## Role requirements (A.2.1)
- MetaAgent#EvidenceAuditor:meta-agent — performs audit
- MetaAgent#AgentDesigner:meta-agent — may provide context on capability intent

## Capability thresholds (A.2.2)
- Performer must have MA.CAP.07 at status ≥ provisional

## Failure semantics
- If evidence record is missing for a capability: result = fail, gap recorded
- If source is inaccessible: result = fail, R downgraded to none
- If F-G-R values are TBD: result = fail, must be filled before audit pass

## Steps
1. For each capability in the table:
   a. Verify evidence link exists and points to valid evidence record
   b. Verify evidence record has non-TBD F-G-R and DecayWindow
   c. Verify source is accessible and supports the claim
   d. Record result: pass / fail
   e. Record notes (what supports the pass, or why it fails)
2. Calculate aggregate metrics:
   - Pass rate: (passed / total) × 100
   - Aggregate F-G-R: weakest-link across all evidence
3. Produce gap list for all failures
4. Recommend capability status upgrades where evidence supports:
   - provisional → smoke-validated: ≥ 80% pass, at least 1 experiment
   - smoke-validated → validated: 100% pass, ≥ 2 experiments, R ≥ medium
5. Record audit as Work (A.15.1) with date, role, duration

## Audit levels (DRR-005)
- **Smoke audit**: Steps 1a-1d only (evidence link exists and has F-G-R)
- **Full audit**: All steps including source verification

## References
- Capability: MA.CAP.07
- Evidence: EXP-001 (Strategator, 10/10 pass)
- Patterns: A.10, B.3, B.3.4, A.15.1
- Decision: DRR-005 (evidence audit requirement)
