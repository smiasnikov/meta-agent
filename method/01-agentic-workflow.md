# Meta-Agent Workflow (MethodDescription)

## Purpose
Describe the future autonomous workflow of the meta-agent (implementation guidance only).

## Inputs
- Applied agent brief (human-approved name + goals)
- Source list (URLs)
- Current capability schema (Level 1/2/3)

## Outputs
- Applied agent capability table
- Evidence stubs and links
- Updated hypothesis + experiment records
- Decision log entry (DRR-lite)

## Steps (B.5 + A.15 + A.10)
1) OBSERVE: parse brief and context boundaries (A.1.1, A.7).
2) ABDUCE: draft capabilities (U.Capability + scope).
3) DEDUCE: define expected work products and checks.
4) INDUCE: map sources to evidence refs; mark gaps.
5) AUDIT: update Evidence Graph and F-G-R + decay.

## Constraints
- No applied-domain knowledge inside meta-agent artifacts.
- Human approval required for applied agent naming.

## Roadmap
- Level 2: add RoleAssignment + MethodDescription refs.
- Level 3: persistent EvidenceGraph IDs and automated F-G-R scoring.
