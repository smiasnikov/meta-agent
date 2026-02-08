# Schema Design (MethodDescription, A.3.2)

## Purpose
Describes the method for defining domain-agnostic KB and dataset schemas for an applied agent.
Linked capability: MA.CAP.05.

## Interface (inputs/outputs)
- **Inputs**: Capability list with WorkScope
- **Outputs**: KB schema (entity types, relations, constraints) + dataset schema (data structures for agent operation)
- **Resources**: FPF skill, A.1 (Holonic Foundation), A.1.1 (BoundedContext)

## Preconditions
- Capability list is available with WorkScope per item
- Applied agent's bounded context is defined

## Postconditions / Effects
- KB schema defines entity types and relations needed by the agent
- Dataset schema defines data structures for inputs, outputs, and intermediate state
- Schemas are domain-agnostic in structure (no applied-domain content)
- Schema is sufficient for agent to operate on its capabilities

## Non-functional constraints
- Structure-only: schemas define shape, not domain content
- Format: markdown with table or structured list

## Role requirements (A.2.1)
- MetaAgent#AgentDesigner:meta-agent — designs schemas

## Capability thresholds (A.2.2)
- Performer must have MA.CAP.05 at status ≥ provisional

## Failure semantics
- If capability requires data structures beyond FPF primitives: record as gap, propose extension
- If schema conflicts with existing applied-agent structure: flag for human review

## Steps
1. For each capability, identify required data entities (inputs, outputs, state)
2. Define entity types using FPF vocabulary (U.System, U.Episteme, etc. where applicable)
3. Define relations between entities
4. Define constraints (required fields, cardinality, type constraints)
5. Produce KB schema document
6. Produce dataset schema document
7. Verify domain-agnosticity: no applied terms in schema definitions

## References
- Capability: MA.CAP.05
- Patterns: A.1, A.1.1, A.7
