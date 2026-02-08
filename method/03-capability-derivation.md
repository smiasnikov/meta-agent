# Capability Derivation (MethodDescription, A.3.2)

## Purpose
Describes the method for deriving U.Capability declarations with WorkScope from a structured requirements list.
Linked capability: MA.CAP.02.

## Interface (inputs/outputs)
- **Inputs**: Structured requirements list (from method/02)
- **Outputs**: Capability list — each item: CapabilityId, Description, Holder, Context, TaskFamily (TBD), WorkScope, WorkMeasures
- **Resources**: FPF skill, A.2.2 schema, bounded-context definitions

## Preconditions
- Requirements list is available and complete (method/02 output)
- A.2.2 capability schema is loaded

## Postconditions / Effects
- Capability list produced with one capability per distinct ability
- Each capability has WorkScope (conditions) and WorkMeasures (targets)
- Capabilities are formulated in positive, measurable terms (A.2.2 didactic guardrail)
- No role words or recipe detail in capability descriptions

## Non-functional constraints
- Domain-agnostic formulation: WorkScope uses structure-only terms
- Capability IDs follow convention: `<PREFIX>.CAP.NN`

## Role requirements (A.2.1)
- MetaAgent#AgentDesigner:meta-agent — executes derivation

## Capability thresholds (A.2.2)
- Performer must have MA.CAP.02 at status ≥ provisional

## Failure semantics
- If a requirement cannot map to a capability: record as gap, flag for review
- If WorkScope cannot be determined: set to "TBD" with explicit note

## Steps
1. Group related requirements by functional area
2. For each group, formulate one capability statement ("System can do X within Y at Z")
3. Define WorkScope: conditions, input types, environment assumptions
4. Define WorkMeasures: measurable targets with thresholds
5. Assign CapabilityId following naming convention
6. Cross-check: no Inputs/Outputs in capability (those go to MethodDescriptions)

## References
- Capability: MA.CAP.02
- Patterns: A.2.2, A.2.6 (USM), A.7
