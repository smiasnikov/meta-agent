# Meta-Agent Workflow (MethodDescription, A.3.2)

## Purpose
Design-time recipe for the meta-agent's agent-creation workflow.

## Inputs
- Applied agent brief (human-approved name + goals)
- Source list (URLs)
- Current capability schema (Level 1/2/3)

## Outputs
- Applied agent capability table
- Evidence stubs and links
- Updated hypothesis + experiment records
- DRR entry (E.9) in changes/decision-log.md

## Steps (B.5 + A.15 + A.10)

| Step | Action | Role (A.2.1) | Patterns |
|------|--------|-------------|----------|
| 1 | OBSERVE: parse brief and context boundaries | MetaAgent#AgentDesigner:meta-agent | A.1.1, A.7 |
| 2 | ABDUCE: draft capabilities (U.Capability + WorkScope) | MetaAgent#AgentDesigner:meta-agent | A.2.2, B.5.2 |
| 3 | DEDUCE: define expected work products and checks | MetaAgent#AgentDesigner:meta-agent | A.15.1 |
| 4 | INDUCE: map sources to evidence refs; mark gaps | MetaAgent#EvidenceAuditor:meta-agent | A.10, B.3 |
| 5 | AUDIT: update Evidence Graph and F-G-R + decay | MetaAgent#EvidenceAuditor:meta-agent | B.3, B.3.4 |

## Constraints
- No applied-domain knowledge inside meta-agent artifacts (DRR-002).
- Human approval required for applied agent naming (DRR-003).

## Roadmap
- Level 2: link TaskFamily to actual MethodDescription files per capability.
- Level 3: persistent EvidenceGraph IDs and automated F-G-R scoring.
