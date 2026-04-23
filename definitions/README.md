# Definitions

This page defines the main terms used in the public findings notes.
It is deliberately short and reader-facing.

## A2A

In this repo, **A2A** means a multi-agent interaction pattern where
named agents exchange task-relevant messages through a shared
application substrate.

## Broker

The **broker** is the upstream agent that carries context from one step
to downstream specialists. In the measured T2 run, that role is played
by `FlightAgent`.

## Fan-out topology

A **fan-out topology** is one where an upstream agent briefs multiple
downstream specialists. In the measured T2 case:

```text
TravelAgent → FlightAgent → {SeatAgent, MealAgent}
```

## Sibling specialists

**Sibling specialists** are downstream agents that share the same
upstream broker but do not directly talk to each other. In the
measured result, `SeatAgent` and `MealAgent` are the sibling pair.

## Coupling

**Coupling** here means narrative overlap or convergence between
agents, measured from their emitted trace text rather than assumed from
the architecture diagram alone.

## S4

**S4** is the repo shorthand for the pairwise overlap statistic used in
the archived run summaries: mean bigram-Jaccard overlap over fixed
windows of the combined in/out narrative stream.

The measured headline result is:

- `MealAgent ↔ SeatAgent`: `S4 = 0.366`

## Direct dialogue channel

A **direct dialogue channel** means one agent explicitly exchanges
messages with another. The T2 sibling finding matters because the two
specialists did **not** have such a direct sibling channel.

## Shared upstream context

**Shared upstream context** means that two downstream agents inherit
briefing material from the same broker, even if they never directly
speak to each other.

## Typed-intent boundary

A **typed-intent boundary** is a stronger pattern derived from the DOP
contrast work: the actionable inter-agent boundary admits normalized
intent or typed structure, not arbitrary free text.

## Free-text inadmissible at the boundary

When this repo says free text is **inadmissible at the boundary**, it
means arbitrary prose is not accepted as a routable or
decision-bearing inter-agent payload. Human ingress may begin as
natural language, but the execution-facing boundary is normalized
before handoff.

## Claim classes

This repo distinguishes:

- **source-backed** claims
- **analytic-inference** claims
- **preliminary** claims
- **held** claims

The formal definitions live in
[evidence/claim-classes.md](../evidence/claim-classes.md).
