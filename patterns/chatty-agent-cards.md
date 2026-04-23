# Anti-pattern: Chatty Agent Cards as Pre-coupling Substrate

*Structural observation derived from the isolated-downstream
adaptation. Proposed as a named anti-pattern for cross-reference into
the Governance Failure Patterns catalogue.*

## Statement

Agent-to-agent systems in which each agent advertises its capability
via free-text natural-language descriptions (commonly called "agent
cards") create a pre-coupling substrate. Downstream agents that never
exchange direct dialogue are nonetheless exposed to each other's
n-gram surface through their cards, via any component (hub, router,
planner, orchestrator) that consumes those cards during routing.

## Mechanism

1. Agent A registers with a natural-language capability description.
2. Agent B registers with a natural-language capability description.
3. A hub or router consumes both descriptions to make routing
   decisions.
4. Context from each card propagates into the routing decisions that
   carry requests to the other agent.
5. N-gram residue from A's card appears in the context window B
   conditions on when processing routed requests — and vice versa.

No direct A↔B dialogue channel is required. The cards are the
channel.

## Relationship to SENTINEL v2's accidental-governance thesis

SENTINEL v2 establishes that probes — out-of-band
identity-reinforcement content visible in the context window —
accidentally functioned as governance by acting as a behavioural
anchor. They suppressed drift 3–6x and doubled self-correction. Gagne
names this the AI Hawthorne effect.

The anti-pattern described here is the **negative image** of that
finding. If probes in the context window accidentally anchor
behaviour in a drift-suppressing direction, chatty agent cards
accidentally anchor behaviour in a drift-inducing direction: the
residual n-gram content of A's card sits in B's context window via
the routing hub and does the opposite of what SENTINEL v2's probes
did — it anchors B toward A's surface vocabulary rather than toward
a stable identity.

Same mechanism, opposite polarity. Both accidental.

The repair — typed intent over public ontology and SHACL shape
validation (see [intent-first-typed-graph.md](./intent-first-typed-graph.md))
— moves the anchoring from accidental to architected, and from
free-text to shape-validated. This is the architected analogue of
SENTINEL v2's accidental anchoring.

Under that repair pattern, free-text routing inputs are not merely
de-emphasised. They are inadmissible at the exchange boundary. If the
router, planner, or orchestrator can still consume free text as a
decision-bearing input, the anti-pattern remains present.

## Empirical basis

The isolated-downstream adaptation of SENTINEL v2 (see
[methods/hub-spoke-vs-mesh.md](../methods/hub-spoke-vs-mesh.md)) is
the configuration in which the mechanism described here is tested.
The current repository does publish a measured indirect-coupling result
in the T2 fan-out topology (see [results/a2a-findings.md](../results/a2a-findings.md)),
but it does not yet isolate the agent-card pathway as the measured
mechanism. This document should therefore still be read as a structural
hypothesis and named anti-pattern proposal rather than as the direct
empirical result itself.

## Why this matters now

The pattern is becoming standardised. Multiple vendor A2A
specifications call for natural-language capability descriptions. At
scale, this means every agent on an A2A network advertises an n-gram
surface that any routing layer can propagate into any other agent's
context window. The substrate for SENTINEL-class coupling collapse is
being built into interoperability standards, alongside the
Hawthorne-style accidental anchoring Gagne identified — neither
effect acknowledged in the current specification drafts.

## Repair: typed shape declarations

Capability advertisements should be expressed as typed graph-line
structures over a shared public ontology, validated by SHACL or an
equivalent shape language. Specifically:

- Capability — a typed node in the ontology, not a paragraph of
  prose.
- Inputs, outputs, preconditions, postconditions — typed properties
  with ontology-referenced ranges.
- Human-readable labels — explicitly bounded and
  non-routing-consumed.
- Routing decisions — computed over the typed structure, not over
  the prose.

See [intent-first-typed-graph.md](./intent-first-typed-graph.md) for
the broader positive pattern.

## Conformance test

A deployment exhibits this anti-pattern if:

1. Any agent's capability advertisement includes unbounded free-text
   description fields.
2. Any routing, planning, or orchestration component consumes those
   fields as input to its decisions, including indirectly via an LLM
   that receives them as context.
3. No typed-shape alternative is available for the routing layer.

A deployment does not exhibit this anti-pattern if capability
advertisements are typed, the routing layer consumes only the typed
form, and any free-text labels are isolated from decision-making
pathways.

Equivalently: if free-text capability descriptions or payloads remain
admissible as routing input at the boundary, the repair has not yet
been implemented in the strong sense claimed here.

## Cross-references

- [GFP F004 Coupled Reasoning Collapse](https://github.com/kevin-biot/governance-failure-patterns/) — the failure class this anti-pattern instantiates.
- [GFP AP012 MCP Direct-to-LLM Tool Coupling](https://github.com/kevin-biot/governance-failure-patterns/) — a related but distinct anti-pattern.
- SENTINEL v2 accidental-governance thesis — the opposite-polarity sibling mechanism. See [references/gagne-sentinel.md](../references/gagne-sentinel.md).
- [Blast Radius Framework](https://github.com/kevin-biot/blast-radius-framework/) — blast-radius-rating implications.
- [methods/hub-spoke-vs-mesh.md](../methods/hub-spoke-vs-mesh.md) — empirical basis.
