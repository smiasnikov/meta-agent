# Requirement Extraction (MethodDescription, A.3.2)

## Purpose
Describes the method for extracting structured requirements from an applied agent brief.
Linked capability: MA.CAP.01.

## Interface (inputs/outputs)
- **Inputs**: Applied agent brief (text, human-approved name + goals)
- **Outputs**: Structured requirements list (each item: ID, description, source ref, priority)
- **Resources**: FPF skill, bounded-context definitions

## Preconditions
- Applied agent name approved by HumanApprover (DRR-003)
- Brief is available as text input
- Meta-agent bounded context is loaded

## Postconditions / Effects
- Requirements list produced with ≥ 80% coverage of brief content
- Each requirement has unique ID and source reference
- No applied-domain knowledge leaks into meta-agent artifacts (DRR-002)

## Non-functional constraints
- Requirements must be domain-agnostic in formulation (structure-only)
- Output format: markdown table or structured list

## Role requirements (A.2.1)
- MetaAgent#AgentDesigner:meta-agent — executes extraction
- Human — provides brief, approves agent name

## Capability thresholds (A.2.2)
- Performer must have MA.CAP.01 at status ≥ provisional

## Failure semantics
- If brief is ambiguous: record gaps explicitly, request clarification from human
- If brief contains no actionable requirements: halt, report to human

## Steps
1. Parse brief text, identify goal statements and constraints
2. Extract each distinct requirement as a separate item
3. Assign unique IDs (REQ-NNN)
4. Map each requirement to brief section (source ref)
5. Flag ambiguities or gaps

## References
- Capability: MA.CAP.01
- Patterns: A.3.2, A.1.1, A.7
