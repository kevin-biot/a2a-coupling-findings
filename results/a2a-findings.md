# A2A Findings

## Headline Finding

In the archived T2 fan-out A2A run

```text
TravelAgent → FlightAgent → {SeatAgent, MealAgent}
```

the two downstream specialists with **no direct dialogue channel**
showed a mean pairwise **S4 = 0.366** across 31 one-minute windows.

That sibling-pair overlap was:

- **1.45×** the mean of the other five agent-pair overlaps in the same
  run
- higher than **FlightAgent ↔ SeatAgent = 0.343**
- higher than **FlightAgent ↔ MealAgent = 0.330**

The siblings agreed more with each other than either did with the
broker that briefed them, despite not speaking directly.

## Why This Matters

This is the core A2A result currently shipped in the repository.

It supports a narrow but important claim:

> In a brokered A2A fan-out topology, coupling can persist through
> shared upstream context even when sibling specialists never directly
> exchange dialogue.

That is the operationally interesting case for real A2A systems. The
question is not only whether fully connected agents couple. It is
whether apparently independent specialists can still converge because
the broker is carrying shared context into both branches.

## Measurement Summary

Derived from the archived DOP run:

- **Run:** `t2-42-20260420T131307Z`
- **Topology:** `TravelAgent → FlightAgent → {SeatAgent, MealAgent}`
- **Agents in scope:** `TravelAgent`, `FlightAgent`, `SeatAgent`,
  `MealAgent`
- **Upstream application counterpart:**
  [kevin-biot/obo-standard](https://github.com/kevin-biot/obo-standard)
  at `examples/integrations/a2a-multi-hop/`
- **Trace source:** windowed analysis of the raw `trace.jsonl`
- **Tokeniser:** `[a-z']+`
- **Windowing:** 60-second fixed windows
- **Pairwise statistic:** mean bigram-Jaccard S4 per pair, using the
  combined in/out narrative stream within each window
- **Windows analysed:** 31

Pairwise means:

| pair | mean S4 |
|---|---|
| FlightAgent ↔ TravelAgent | 0.496 |
| **MealAgent ↔ SeatAgent** | **0.366** |
| FlightAgent ↔ SeatAgent | 0.343 |
| FlightAgent ↔ MealAgent | 0.330 |
| MealAgent ↔ TravelAgent | 0.048 |
| SeatAgent ↔ TravelAgent | 0.048 |

Machine-readable table:

- [results/data/t2_pairwise_s4.tsv](./data/t2_pairwise_s4.tsv)

The key point is not that the sibling pair is the highest pair overall.
It is that the sibling pair remains strongly coupled **without a direct
sibling channel**, and exceeds each sibling's overlap with the broker.
The current public note therefore identifies both the measured topology
and the concrete agent set, rather than leaving them implicit.

## Relationship To The Broader A2A Program

This finding sits alongside two supporting contrasts from the DOP
archive:

- **T1 chain result:** free-NL chain topology measured around
  **S4 ≈ 0.30** across 5 seeds
- **DOP typed-intent contrast:** typed-intent DOP topology measured
  **S4 = 0.000** across 300 windows × 5 seeds

Those contrasts are useful, but they are secondary here. The primary
publication point is the sibling-coupling result in the fan-out case.

## Scope And Status

This finding is **measured** but **preliminary**.

Why preliminary:

- it is based on an archived DOP A2A run rather than a separately
  pre-registered public experiment line for this repo
- the run is currently single-seed
- the stricter isolated-downstream replication line documented in
  [methods/hub-spoke-vs-mesh.md](../methods/hub-spoke-vs-mesh.md) is a
  related but separate method path

What can be claimed:

- sibling specialists coupled strongly in this measured T2 run
- the coupling persisted without a direct sibling dialogue channel
- shared-broker fan-out is therefore a real A2A coupling surface

What cannot yet be claimed from this note alone:

- a general universal baseline for all isolated A2A topologies
- a pre-registered replication-grade verdict for the stricter
  SENTINEL-v2-style isolated-downstream comparison line

## Interpretation Boundary

The measured result supports the mechanism-level inference that
**indirect pathways matter**. In this run, the plausible pathway is the
shared upstream briefing carried by `FlightAgent` into both specialist
branches.

The stronger "chatty agent cards" claim remains a downstream structural
inference, not the direct measured result of this note.

## Bottom Line

The current public A2A finding is not hypothetical:

> **T2 fan-out siblings measured S4 = 0.366 despite no direct sibling
> dialogue, indicating real coupling through shared-broker context.**

That is the result this repository should lead with today.
