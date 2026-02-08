# Template Production (MethodDescription, A.3.2)

## Purpose
Describes the method for producing MethodDescription and Work templates for an applied agent.
Linked capability: MA.CAP.03.

## Interface (inputs/outputs)
- **Inputs**: Capability list (from method/03)
- **Outputs**: MethodDescription templates (one per capability) + Work record template
- **Resources**: FPF skill, A.3.2 structure, A.15.1 Work structure

## Preconditions
- Capability list is available with WorkScope and WorkMeasures per item
- A.3.2 MethodDescription structure and A.15.1 Work structure are loaded

## Postconditions / Effects
- One MethodDescription template per capability, following A.3.2:4.3 content prompts
- One Work record template following A.15.1
- Templates are FPF-conformant (A.7 distinctions maintained)
- TaskFamily links in capability table can now reference actual files

## Non-functional constraints
- Templates must be domain-agnostic (structure only, no applied content)
- Format: markdown files in applied agent's method/ directory

## Role requirements (A.2.1)
- MetaAgent#AgentDesigner:meta-agent — produces templates

## Capability thresholds (A.2.2)
- Performer must have MA.CAP.03 at status ≥ provisional

## Failure semantics
- If capability has no clear procedural decomposition: create minimal template with Purpose + Interface + Role only
- If A.7 violation detected in template: flag and correct before output

## Steps
1. For each capability, create MethodDescription file with A.3.2:4.3 fields:
   - Purpose (link to capability)
   - Interface (inputs/outputs/resources)
   - Preconditions, Postconditions
   - Role requirements, Capability thresholds
   - Failure semantics
2. Create Work record template with A.15.1 fields:
   - Date, Role, Duration
   - Inputs consumed, Outputs produced
   - Deviations from MethodDescription
3. Verify no schedule, assignees, or BoM in templates (A.3.2 guardrail)

## References
- Capability: MA.CAP.03
- Patterns: A.3.2, A.15.1, A.7
