# Evidence Design (MethodDescription, A.3.2)

## Purpose
Describes the method for designing an evidence scheme and validation workflow for an applied agent's capabilities.
Linked capability: MA.CAP.04.

## Interface (inputs/outputs)
- **Inputs**: Capability list with WorkScope and WorkMeasures
- **Outputs**: Evidence scheme (which evidence items validate which capabilities) + validation workflow (how to run audits)
- **Resources**: FPF skill, A.10, B.3, B.3.4

## Preconditions
- Capability list is available (method/03 output)
- Source list for applied agent is available

## Postconditions / Effects
- Evidence scheme maps each capability to ≥ 1 evidence item
- Each evidence item has: Claim supported, Source, F-G-R, DecayWindow
- Validation workflow defines audit steps and acceptance criteria
- Evidence IDs follow naming convention (`<PREFIX>.EV-NNN`)

## Non-functional constraints
- Evidence scheme is domain-agnostic in structure (domain sources are referenced, not embedded)
- F-G-R values must be at least provisional (not TBD)

## Role requirements (A.2.1)
- MetaAgent#AgentDesigner:meta-agent — designs scheme
- MetaAgent#EvidenceAuditor:meta-agent — reviews scheme for A.10 conformance

## Capability thresholds (A.2.2)
- Performer must have MA.CAP.04 at status ≥ provisional

## Failure semantics
- If a capability has no identifiable evidence source: record as gap, set R = none
- If F-G-R cannot be estimated: set F = F0, G = local, R = low with explicit note

## Steps
1. For each capability, identify which source(s) can support the claim
2. Create evidence stub for each capability-source pair (using _evidence-template.md)
3. Assign F-G-R values based on source quality:
   - F: formality of source (F0 = anecdotal, F1 = informal doc, F2 = structured)
   - G: claim scope (which context does evidence cover?)
   - R: reliability (low/smoke/medium/high)
4. Set DecayWindow per evidence item
5. Design validation workflow: sequence of audit steps, acceptance threshold
6. Cross-check: every capability has ≥ 1 evidence link

## References
- Capability: MA.CAP.04
- Patterns: A.10, B.3, B.3.4, A.2.4 (EvidenceRole)
