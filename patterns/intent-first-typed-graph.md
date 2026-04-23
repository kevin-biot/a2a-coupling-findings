# Pattern: Intent-First, Typed Graph-Line A2A (Architected Anchoring)

*The positive architectural move corresponding to the failure modes
observed in this work. Positioned as the architected analogue of
SENTINEL v2's accidental-governance finding.*

## Statement

Agent-to-agent interactions should exchange **typed intent** expressed
as graph-line structures over a public ontology, validated by SHACL
shapes at exchange boundaries. Natural-language payloads should be
confined to human-visible surfaces and excluded from the
decision-making path.

Operationally, this means **free-text inter-agent payloads are
inadmissible at the input boundary** under the pattern. If a message
arrives as unbounded natural language rather than as a conformant typed
graph-line structure, the boundary rejects it rather than routing or
interpreting it.

In the stronger DOP-derived form of the pattern, this also means the
agent side is **not given raw tool exposure as the interchange model**.
What crosses the execution boundary is a normalized intent / typed
structure, not free text plus open-ended tool choice.

## Relationship to SENTINEL v2's accidental-governance thesis

SENTINEL v2 establishes empirically that probes — out-of-band
identity-reinforcement content visible in the context window —
accidentally functioned as governance by acting as a behavioural
anchor. Gagne names this the AI Hawthorne effect and characterises
it as: compliance monitoring is not just measuring behaviour; it is
changing it.

SENTINEL v2's empirical contribution establishes one thing clearly:
**anchoring works**.

The intent-first typed-graph-line pattern is the **architected
analogue**. It moves the anchor from the incidental content of
monitoring probes to the required shape of the exchange boundary.
Where SENTINEL v2's anchoring is accidental, free-text, unverifiable,
and probe-side, the pattern here is deliberate, typed,
SHACL-verifiable, and boundary-side.

The two framings compose cleanly:

- SENTINEL v2 proves the mechanism works, accidentally.
- This pattern proposes the mechanism be intentional,
  third-party-verifiable, and failure-closed.

## Why this repairs the observed failure modes

The isolated-downstream adaptation identifies two coupling pathways
that persist even without a direct dialogue channel between
downstream agents:

1. Chatty agent cards (pre-exposure substrate).
2. Natural-language payload content carried between agents by the
   routing layer.

Typed intent over a public ontology closes both:

1. Cards become typed shape declarations — no n-gram surface to
   mirror.
2. Payloads become typed graph-line structures — no free-text channel
   for n-gram accumulation.

SHACL validation at the exchange boundary enforces the typing rather
than relying on each agent's good behaviour. Non-conformant messages
fail closed.

That failure-closed rule applies at ingress, not only after parsing:
free text is not a valid interchange form under the pattern. It is not
"allowed but discouraged"; it is inadmissible at the exchange boundary.

## What this is and is not

**Is:**

- An architectural pattern for the A2A exchange boundary.
- A concrete specification target: ontology classes + SHACL shapes +
  validation gates.
- Verifiable by a third party. Conformance — does the boundary admit
  unbounded natural language? — is a yes/no question with a
  repeatable test.

**Is not:**

- A claim that SHACL alone is sufficient. Two agents can exchange
  well-formed but semantically adversarial typed graphs and SHACL
  will pass them. Shape validation closes the malformed-input
  pathway; it does not close semantic attack.
- A full vaccine. The vaccine stack is ontology + SHACL +
  behavioural constraints. SHACL is the verifiable-by-others
  component.
- A claim of novelty for typed-interface or shape-validation
  technologies. Typed interprocess contracts, schema validation, and
  shape languages are established technologies. The novelty is the
  framing — that these are the architected analogue of SENTINEL v2's
  accidental-governance finding, and that their deliberate
  deployment at the A2A exchange boundary closes the coupling
  channel SENTINEL identifies.

## Composition with the vaccine stack

The full repair pattern composes three layers:

1. **Bounded vocabulary** — the public ontology declares what kinds
   of things can be talked about between agents. The antigen shape.
2. **Shape validation** — SHACL shapes enforce the vocabulary at
   every exchange boundary. The recognition gate. Fails closed.
3. **Behavioural constraints** — bounded action classes constrain
   what an agent is permitted to do with a validated message. The
   immune response.

Publishing SHACL alone understates the architecture and is
attackable via well-formed adversarial graphs. The stack is the
vaccine.

One practical consequence should be stated plainly: a boundary that
admits arbitrary free text as a routable input does **not** implement
this pattern, even if it also publishes ontology terms or SHACL
shapes.

Likewise, a boundary that exposes raw tool invocation as the peer-agent
control surface has not implemented the stronger inverted-A2A form of
the pattern documented in this repository's DOP lineage notes.

## Publication status

- Public ontology and SHACL shapes — published separately as
  [PACT-public](https://github.com/kevin-biot/pact-public);
  cross-referenced here. This is the public pack-shape surface, not a
  claim that the exact DOP test packs are published unchanged.
- Two worked A2A examples (what shapes block, what passes) —
  published alongside the ontology.
- Conformance test (does your A2A boundary admit unbounded natural
  language?) — published alongside the ontology.
- Behavioural-constraint framework — published in its own companion
  surface; cross-referenced here.
- Derivation lineage from the DOP typed-intent / ontology rig —
  documented in
  [derivations/dop-rig-to-vaccine-claims.md](../derivations/dop-rig-to-vaccine-claims.md).

## Cross-references

- SENTINEL v2 accidental-governance thesis — the empirical basis for
  the anchoring-works claim this pattern architects. See
  [references/gagne-sentinel.md](../references/gagne-sentinel.md).
- [GFP F004 Coupled Reasoning Collapse](https://github.com/kevin-biot/governance-failure-patterns/) — failure class this pattern repairs.
- [GFP AP012 MCP Direct-to-LLM Tool Coupling](https://github.com/kevin-biot/governance-failure-patterns/) — anti-pattern this displaces.
- [chatty-agent-cards.md](./chatty-agent-cards.md) — the anti-pattern
  this pattern's card-side repairs.
- [Blast Radius Framework](https://github.com/kevin-biot/blast-radius-framework/) — blast-radius-rating effect.
