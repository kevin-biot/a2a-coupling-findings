# A2A Coupling Findings

This repository is a public evidence pack about **coupling in
A2A-style multi-agent systems**. The primary finding currently shipped
here is a measured **fan-out sibling-coupling** result: in a brokered
A2A topology, two downstream specialists with no direct dialogue
channel still converged strongly via shared upstream context.

The primary publication target is the **A2A finding**. The DOP
typed-intent stack appears only as a **secondary contrast case** where
it helps interpret the A2A result; it is not the main story of this
repo.

## Read First

- [results/a2a-findings.md](./results/a2a-findings.md) — primary A2A
  findings note.
- [results/README.md](./results/README.md) — what counts as the primary
  result versus supporting background.
- [methods/t2-fanout-coupling.md](./methods/t2-fanout-coupling.md) —
  method and provenance for the current measured A2A result.
- [evidence/claim-classes.md](./evidence/claim-classes.md) — claim
  discipline for what is measured, inferred, or still provisional.
- [definitions/README.md](./definitions/README.md) — compact glossary
  for the core terms used in the findings note.
- [TASK-PLAN.md](./TASK-PLAN.md) — current cleanup and publication plan.

## Upstream A2A Implementation

The current measured A2A finding was not produced from code authored in
this repo alone. Its upstream application counterpart lives in:

- [kevin-biot/obo-standard](https://github.com/kevin-biot/obo-standard)
- path: `examples/integrations/a2a-multi-hop/`

The concrete agents used for the current measured **T2** fan-out result
were:

- `TravelAgent`
- `FlightAgent`
- `SeatAgent`
- `MealAgent`

For reference, the supporting **T1** chain variant used the same stack
without `MealAgent`, i.e. `TravelAgent → FlightAgent → SeatAgent`.
This public repo publishes the findings layer, not the full upstream
application code or raw trace archive.

## Repository Map

- [results/](./results/) — empirical findings and supporting result
  notes. This is the primary reading path.
- [methods/](./methods/) — how the current A2A result was derived and
  how the stricter replication line is defined.
- [evidence/](./evidence/) — provenance and claim-boundary discipline.
- [definitions/](./definitions/) — reader-facing vocabulary and
  concept definitions used in the findings notes.
- [preregistration/](./preregistration/) — pre-registration material
  for the supporting SENTINEL re-analysis.
- [patterns/](./patterns/) — secondary anti-pattern and repair-pattern
  notes. Useful, but not the headline evidence surface.
- [derivations/](./derivations/) — explicit lineage notes for
  secondary repair-pattern / vaccine claims derived from the DOP rig.
- [references/](./references/) — primary external anchor and citation
  context.

## Current Publication Stance

- **Primary:** A2A coupling findings and their evidence boundary.
- **Secondary:** supporting re-analysis of SENTINEL and any DOP-based
  comparator material.
- **Tertiary:** companion architecture and standards framing.

The repo should read in that order. If a document does not help defend
the A2A claim directly, it belongs off the critical path.

The current primary A2A result is a **preliminary but measured**
fan-out finding. A stricter isolated-downstream replication line remains
separate and is documented as related future work rather than as a
landed headline result.

## Disclosure Boundary

This repo publishes findings text, attribution, claim boundaries, and
method descriptions. Some detector implementation details are not
included here. Where a result depends on a published external metric
definition, the relevant document states that explicitly and cites the
source.

## Companion Public Surfaces

- [Blast Radius Framework](https://github.com/kevin-biot/blast-radius-framework)
- [Governance Failure Patterns](https://github.com/kevin-biot/governance-failure-patterns)
- [PACT-public](https://github.com/kevin-biot/pact-public) — ontology
  pack / SHACL-shape companion for inspecting the public pack form

## License

Text under Creative Commons Attribution 4.0 International (CC-BY-4.0).
See [LICENSE](./LICENSE).

Primary external dependency attribution is in
[ATTRIBUTION.md](./ATTRIBUTION.md).
