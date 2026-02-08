# Meta-Agent (Overview)

## Purpose
Meta-agent designs applied agents using FPF structures and evidence discipline.

## Boundary rules
- No applied-domain knowledge inside meta-agent artifacts.
- Applied content lives in applied agent folders or in meta-agent experiments/hypotheses as test data only.
- Applied agent naming requires explicit human approval.

## Directory structure (meta-agent)
- bounded-context/      Context scope, entities, distinctions
- capabilities/         Meta-agent capabilities (A.2.2 schema)
- hypotheses/           Hypotheses about agent creation process
- experiments/          Experiment records (Work per A.15.1)
- sources/              Evidence templates and meta-agent sources
- changes/              Decision log (DRR per E.9)
- method/               MethodDescriptions (design-time recipes)

## References
- BoundedContext → bounded-context/00-index.md
- Capabilities → capabilities/meta-agent.md
- Decision log → changes/decision-log.md
- Operational rules → AGENTS.md
- Workflow → method/01-agentic-workflow.md
