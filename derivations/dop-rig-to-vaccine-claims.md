# DOP Rig to Vaccine-Claim Lineage

This note makes explicit how the repository's **vaccine-stack** or
**repair-pattern** language was derived.

## Why this note exists

The current public repo leads with an A2A empirical finding:

- T2 fan-out siblings coupled despite no direct sibling dialogue
  channel.

But some secondary claims in the repo go beyond that measured A2A
result:

- typed intent over a public ontology as the repair direction
- SHACL validation as the boundary-side verification mechanism
- behavioural constraints as the third layer of the stack
- the framing of the full composition as a "vaccine"

Those claims were not invented from the A2A run alone. They were
derived from the contrast between the A2A coupling observations and the
separately developed DOP runtime architecture.

## The source rig

The repair-pattern lineage comes from the DOP typed-intent / ontology
runtime and its observability rig, not from the free-NL A2A topology
itself.

Key source artifacts in the private/public DOP worktree:

- `DOP/cmd/dop-dashboard/main.go` — dual-gaze dashboard
  implementation
- `DOP/cmd/dop-integration/main.go` — 16-service integration wiring
  and dashboard poll surface
- `DOP/scripts/dop-218-demo-walkthrough.sh` — demo script for the four
  cross-gaze cases
- `DOP/docs/adr/DOP-232-dual-gaze-metrics-endpoint-coverage.md` —
  acceptance evidence for 16/16 dashboard coverage during the soak
- `DOP/docker-compose.obo-integration.yml` — one of the reconstructible
  runtime bundles for DOP-side OBO integration

## Test-specific ontology and runtime shape

The DOP-side comparison rig was not run against an abstract or
unspecified vocabulary. The test stack loads a **specific seeded banking
pack**:

- `DOP/docker-compose.obo-integration.yml` runs the DOP services with
  `DOP_PROTOCOL_MODE: "obo"` and `--seed-dir /app/packs/banking/seed`
- `DOP/packs/banking/seed/` contains the synthetic banking test corpus
  used by the runtime
- `DOP/docs/adr/DOP-110-synthetic-testing-ecosystem.md` describes the
  synthetic domain ontologies, seed data, and integration scenarios

The ontology side is also concrete rather than generic. In the sibling
`ontology` repo, the banking registry family includes:

- `registry/banking`
- `registry/banking-router`
- `registry/banking-account-query`
- `registry/banking-compliance`
- `registry/banking-loan-query`
- `registry/banking-recurring-payment`

At the time of this review, the local ontology worktree is at commit
`b1b57aa` (`Add dual-gaze metrics endpoint for registry-static`).

For reader-facing inspection of **pack shape**, the public companion
repo is:

- [kevin-biot/pact-public](https://github.com/kevin-biot/pact-public)

That public repo is the right place to inspect the published form of
ontology packs, SHACL-bound artifacts, and open-pack-facing structure.
It should not be read as a claim that the exact concrete banking test
packs used in the DOP rig are published there unchanged.

So the repair framing is not "generic ontology solves it." The lineage
comes from a concrete, domain-scoped test stack with a declared banking
pack and bounded execution surface.

## Inversion of the default A2A posture

The DOP pattern also differs from common A2A designs in a more specific
way than the current repo states.

It **inverts the usual A2A boundary**:

- the user-facing side may begin from natural language at ingestion
- the execution side does **not** admit arbitrary free text as the
  inter-agent control form
- the agent/LLM side does **not** receive raw tool execution freedom
- the operative routing unit is the resolved / normalized
  `intent_class`, not a free-text capability exchange

Supporting evidence in the DOP worktree:

- `DOP/tests/integration/llm_telco_test.go` states that the LLM does
  **not** call tools directly; it must call `dop_pipeline_run` and is
  forbidden from emitting `tool_id` or `parameters`
- `DOP/docs/adr/DOP-095-domain-scope-runtime-modes.md` records the move
  away from direct LLM-to-tool access toward template-driven,
  deterministic execution
- `DOP/use-cases/README.md` treats `sample-intents.json` as the
  canonical representative artifact for normalized intent
- `DOP/cmd/dop-server/main.go` exposes `/api/v1/session/capabilities`
  as a session-scoped manifest endpoint, which is a different thing
  from granting peers raw tool execution at the boundary

This is the operational meaning of the repair pattern in DOP terms:

> free text may exist at human ingress, but it is not the admissible
> inter-agent execution form; normalized intent is.

## The derivation step

The logic chain is:

1. The A2A runs show that free-natural-language exchange surfaces allow
   coupling to persist even when dialogue visibility is reduced.
2. The DOP rig shows a different architectural substrate:
   typed intent, ontology-bounded vocabulary, explicit service roles,
   no raw tool exposure on the agent path, and boundary-side controls.
3. The DOP stack's public-facing control surfaces make the boundary
   contract inspectable rather than implicit.
4. Therefore the proposed repair is not "more monitoring" inside free
   language exchange, but replacing the exchange substrate with typed,
   bounded, externally verifiable structures.

That is where the repository's repair framing comes from.

## What is measured versus derived

Measured directly in this repo:

- T2 sibling coupling in the A2A fan-out case

Measured in the broader DOP line:

- stable segmented service/runtime behavior under the DOP typed-intent
  stack
- dual-gaze dashboard coverage and live-soak observability on the DOP
  side

Derived analytically from those sources:

- ontology as the bounded vocabulary layer
- SHACL as the exchange-boundary recognition gate
- behavioural constraints as the third control layer
- the "vaccine-stack" framing for the three-layer composition

## Claim boundary

This note does **not** claim that the DOP dashboard alone proves the
vaccine stack prevents all future coupling. That would overstate the
evidence.

What it does claim is narrower:

> the repository's repair-pattern language is grounded in a real DOP
> runtime and observability rig, not just post-hoc rhetoric added to
> the A2A findings.

The stack remains a **secondary architectural claim** in this repo,
classified as analytic inference rather than as the primary measured
finding.

## Cross-references

- [patterns/intent-first-typed-graph.md](../patterns/intent-first-typed-graph.md)
  — the repair pattern itself
- [patterns/chatty-agent-cards.md](../patterns/chatty-agent-cards.md)
  — the negative image / anti-pattern side
- [evidence/claim-classes.md](../evidence/claim-classes.md)
  — classification discipline for measured versus derived claims
