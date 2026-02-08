# Required Distinctions (A.7)

## Core separations
- Object ≠ Description ≠ Carrier
- Role ≠ Work
- MethodDescription ≠ Method ≠ Work
- **Capability ≠ Method** — Capability is "can do X within WorkScope" (A.2.2); Method is "how to do X" (A.3)

## Meta-agent boundary
- Meta-agent does **not** contain applied-domain knowledge (DRR-002).
- Applied agents contain domain knowledge and live outside meta-agent context.

## Project-specific anti-patterns (litmus tests)
- Do NOT put Inputs/Outputs in capability tables — those belong in MethodDescriptions.
- Do NOT reference applied evidence (ST.EV-NNN) without context prefix.
- Do NOT upgrade capability status without evidence audit (DRR-005).
- Do NOT mix Problem frame with Decision in DRR records — they are separate E.9 components.

## Usage
- Any rule that depends on applied practice must be placed in applied agent folders.
- Experiments/hypotheses may reference applied agents as test cases only.

## References
- Scope → [01-scope.md](01-scope.md)
- Entities → [02-entities.md](02-entities.md)
- Decision: DRR-002 (boundary), DRR-006 (DRR format)
