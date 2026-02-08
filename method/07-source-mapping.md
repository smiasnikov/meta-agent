# Source Mapping (MethodDescription, A.3.2)

## Purpose
Describes the method for mapping domain sources into FPF slots (evidence refs, capability support).
Linked capability: MA.CAP.06.

## Interface (inputs/outputs)
- **Inputs**: Source list (URLs, documents, references) + capability list + evidence scheme
- **Outputs**: Mapping table (source → FPF slot) with coverage metrics
- **Resources**: FPF skill, A.10, B.3

## Preconditions
- Source list is available
- Capability list and evidence scheme are available (method/03, method/05 outputs)

## Postconditions / Effects
- Each source mapped to ≥ 1 FPF slot (capability evidence, method support, or context definition)
- Coverage metric: ≥ 80% sources mapped
- Unmapped sources explicitly flagged with reason

## Non-functional constraints
- Mapping is structural: meta-agent records WHICH source supports WHICH claim, not domain content
- Source content is not copied into meta-agent artifacts (DRR-002)

## Role requirements (A.2.1)
- MetaAgent#AgentDesigner:meta-agent — performs mapping
- MetaAgent#EvidenceAuditor:meta-agent — validates mapping quality

## Capability thresholds (A.2.2)
- Performer must have MA.CAP.06 at status ≥ provisional

## Failure semantics
- If source is inaccessible: record as gap, set evidence R = none
- If source does not support any capability: mark as "context-only" or "excluded" with reason

## Steps
1. For each source, identify which capability claims it can support
2. For each mapping, create or update evidence record (using _evidence-template.md)
3. Assign F-G-R to each source-capability link:
   - F: based on source formality (textbook vs. blog vs. paper)
   - G: scope of claim the source supports
   - R: source reliability
4. Calculate coverage: (mapped sources / total sources) × 100
5. Flag unmapped sources with reason
6. Update evidence scheme with new mappings

## References
- Capability: MA.CAP.06
- Patterns: A.10, B.3, B.3.4, A.7
