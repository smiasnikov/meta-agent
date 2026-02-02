# Capabilities: Meta-Agent (Level 1 — Provisional)

All capabilities are provisional and must be validated by evidence (A.10 / B.3 / B.3.4).

## Level 1 schema (current)
Fields:
- CapabilityId
- Description
- Scope (A.2.6)
- Inputs
- Outputs
- Preconditions
- Postconditions
- Evidence (A.10)
- F-G-R (B.3)
- DecayWindow (B.3.4)
- Status

## Capability table

| CapabilityId | Description | Scope | Inputs | Outputs | Preconditions | Postconditions | Evidence | F-G-R | DecayWindow | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| MA.CAP.01 | Extract requirements from agent descriptions | Any domain; text-only | Agent brief | Structured requirements | Brief present | Requirements list produced | TBD | TBD | TBD | provisional |
| MA.CAP.02 | Derive U.Capability + scope for applied agents | Any domain; structure-only | Requirements | Capability list | Requirements list | Capabilities w/ scope | TBD | TBD | TBD | provisional |
| MA.CAP.03 | Produce MethodDescriptions and Work templates | FPF-only | Capability list | Templates | Capability list | Templates created | TBD | TBD | TBD | provisional |
| MA.CAP.04 | Design evidence scheme and validation workflow | FPF-only | Capabilities | Evidence scheme | Capabilities list | Evidence schema | TBD | TBD | TBD | provisional |
| MA.CAP.05 | Define KB and dataset schemas (domain-agnostic) | FPF-only | Capabilities | Schema | Capabilities list | Schema created | TBD | TBD | TBD | provisional |
| MA.CAP.06 | Map domain sources into FPF slots | Structure-only | Sources list | Mappings | Sources list | Mappings created | TBD | TBD | TBD | provisional |
| MA.CAP.07 | Perform evidence audit of applied capabilities | FPF-only | Capability table + evidence records + sources | Audit report | Evidence records exist | Pass/fail + gaps recorded | TBD | TBD | TBD | provisional |

## Roadmap (future formalization)
- **Level 2**: add RoleAssignment (A.2.1) and MethodDescription refs (A.3.2).
- **Level 3**: represent capabilities as U.Capability objects with EvidenceGraph IDs.

## Notes
- No applied-domain knowledge in this file.

## References
- BoundedContext → ../bounded-context/00-index.md
