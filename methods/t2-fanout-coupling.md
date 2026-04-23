# T2 Fan-out Coupling Method

This note defines the method and provenance for the **current primary
A2A finding** in the repository.

## Topology

The measured run used a brokered fan-out topology:

```text
TravelAgent → FlightAgent → {SeatAgent, MealAgent}
```

Key property:

- `SeatAgent` and `MealAgent` do **not** directly exchange dialogue
- both receive work from the same upstream broker, `FlightAgent`

This is the structural reason the result matters. The sibling pair can
appear independent at the dialogue layer while still inheriting shared
context from the same upstream branch.

## Archive Provenance

The primary measurement in [results/a2a-findings.md](../results/a2a-findings.md)
was derived from the archived DOP research run:

- private archive root: `DOP/research/sentinel-a2a/agent-topology-comparison/`
- run id: `t2-42-20260420T131307Z`
- raw trace artefact: `data/runs/t2-42-20260420T131307Z/trace.jsonl`

This repository does not vendor the raw trace. It publishes the result
statement and method boundary.

## Upstream Code And Agent Set

The measured topology was exercised against the upstream A2A example
stack maintained separately at:

- [kevin-biot/obo-standard](https://github.com/kevin-biot/obo-standard)
- path: `examples/integrations/a2a-multi-hop/`

The DOP archive identifies the corresponding upstream files as:

- `agents.py` — `TravelAgent`, `FlightAgent`, `SeatAgent`,
  `MealAgent`
- `docker-compose.yml` — `t1` and `t2` profiles for the measured
  topologies

Agent scope for the current public result:

- **T2 fan-out:** `TravelAgent`, `FlightAgent`, `SeatAgent`,
  `MealAgent`
- **T1 chain support case:** `TravelAgent`, `FlightAgent`,
  `SeatAgent`

This public repo publishes the findings and method boundary, not the
full upstream application code.

## Computation Rule

The reported sibling-coupling value is:

- **pairwise S4**
- computed as **bigram Jaccard overlap**
- over the **combined in/out narrative stream**
- within **60-second windows**
- then averaged across all windows for the target pair

Tokeniser:

- regex `[a-z']+`

Window count:

- 31 windows

This is the same signal family used throughout the DOP `sentinel-a2a`
work: lexical mirroring as a substrate-coupling indicator.

## Reported Pairwise Means

For the T2 run, the windowed all-directions pairwise means were:

| pair | mean S4 |
|---|---|
| FlightAgent ↔ TravelAgent | 0.496 |
| MealAgent ↔ SeatAgent | 0.366 |
| FlightAgent ↔ SeatAgent | 0.343 |
| FlightAgent ↔ MealAgent | 0.330 |
| MealAgent ↔ TravelAgent | 0.048 |
| SeatAgent ↔ TravelAgent | 0.048 |

The sibling pair (`MealAgent ↔ SeatAgent`) is therefore:

- above each sibling-to-broker specialist pair
- **1.45×** the mean of the other five pairs

## Status

This method note supports a **preliminary measured finding**.

It is not the same thing as the stricter isolated-downstream method
described in [hub-spoke-vs-mesh.md](./hub-spoke-vs-mesh.md), which
remains a related replication line rather than the current headline
result.
