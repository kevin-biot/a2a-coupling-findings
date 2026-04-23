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

## SENTINEL signal vocabulary

This repo inherits part of a broader **SENTINEL** signal vocabulary.
Readers may encounter references to `G*` labels in the supporting
materials or in the upstream lineage.

For the current public repo surface:

- **G5** is the only `G*` signal used directly in the supporting
  re-analysis path.
- **4-gram overlap** is the other named SENTINEL signal that matters
  directly here.
- other `G*` labels belong to the broader upstream signal family, but
  are not independently defined or used as headline measures in this
  repo.

The published signal catalogue we rely on is summarized in
[references/gagne-sentinel.md](../references/gagne-sentinel.md) and
discussed operationally in
[methods/signal-class-description.md](../methods/signal-class-description.md).

## G5

**G5** is SENTINEL's Shannon-diversity signal over vocabulary and
sentiment. In this repo it appears on the supporting SENTINEL
re-analysis path as the published collapse-class reference signal.

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
