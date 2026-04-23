# Isolated-Downstream A2A — Related Replication Line

*Core methodological distinction between SENTINEL v2's configuration
and the adaptation used in this work.*

This note describes a **related, stricter replication line** for the
same broad indirect-coupling question. It is not the source of the
current primary measured finding in this repository; that finding comes
from the T2 fan-out result documented in
[t2-fanout-coupling.md](./t2-fanout-coupling.md).

## SENTINEL v2's configuration

SENTINEL v2 is configured as:

- **Hardware layout:** hub-and-spoke across NVIDIA Jetson Orin Nano
  nodes, with 12 distributed analyzers.
- **Agent connectivity:** full-mesh at the dialogue layer.
- **Experimental scale:** 10-agent archetypes, 23 distributed
  experiments, 20,000+ messages, 58,000+ probes, 13,800+
  calibrations.

Under this configuration, coupling channels available include:

- Direct agent-to-agent message visibility within the mesh.
- Shared context accumulation across all participants.
- N-gram mirroring pathways between any pair of agents in the mesh.

SENTINEL v2's published 4-gram overlap characterises both conditions
directly:

- **Group condition (full-mesh connected):** 80% 4-gram overlap.
- **Isolated condition:** 14–18% 4-gram overlap baseline.

## This work's adaptation

We retain SENTINEL v2's hub-and-spoke hardware layout and
configuration discipline. We modify the **agent-connectivity layer**
only: two downstream agents with no direct visibility of each other's
dialogue, separated by an upstream routing hub.

- An upstream agent (hub / router / coordinator) handles all incoming
  requests and routes them to downstream agents.
- Two downstream agents receive routed tasks.
- The two downstream agents have no direct visibility of each other's
  dialogue. Neither observes the other's messages, replies, or
  conversational context.
- Shared surfaces between the two downstream agents are limited to:
  1. The upstream hub's routing behaviour, which carries context
     fragments across calls to support intelligent routing.
  2. The agent-card advertisement layer — free-text natural-language
     capability descriptions each downstream agent published at
     registration, consumed by the hub during routing.

This is not a novel hardware topology. SENTINEL v2 already runs
hub-and-spoke hardware. The adaptation is at the agent-connectivity
layer: we remove the full-mesh dialogue-visibility channel between
downstream agents while preserving every other element of the
configuration.

## Why the distinction matters

SENTINEL v2's mesh-connected result admits a defensive reading: "do
not fully mesh-connect agents at the dialogue layer; remove the
direct-visibility channel and the coupling channel closes." The
isolated-downstream adaptation tests whether that reading holds.

Almost no production A2A deployment is full-mesh at the
agent-connectivity layer. The common patterns are hub-and-spoke at
that layer too (coordinator plus workers, planner plus executors),
chained (pipeline), or orchestrated. If coupling requires mesh
agent-connectivity, the SENTINEL v2 finding bounds the problem to an
atypical deployment shape. If coupling does not require mesh
agent-connectivity, the finding applies to the common production
patterns.

## The prediction tested

SENTINEL v2's isolated baseline for 4-gram overlap is 14–18%. If two
downstream agents isolated at the dialogue layer — but sharing a hub
and having exchanged free-text agent cards during registration — show
4-gram overlap materially above 14–18%, that is evidence of indirect
coupling via the hub and the card layer.

The finding claim is a number against a number, not a narrative.

## Pathways implicated if indirect coupling is observed

Conditional on the measurement coming in above baseline:

1. **Hub context-carrying.** The upstream router cannot route
   intelligently without preserving some request/response context
   across calls; n-gram residue can leak through that preservation
   layer.
2. **Chatty agent-card advertisements.** Free-text capability
   descriptions become a pre-exposure channel — each downstream agent
   has been seen by the other via its card, before any traffic flows.
   See [patterns/chatty-agent-cards.md](../patterns/chatty-agent-cards.md).

## Disclosure boundary

The specific measure used to detect bigram and n-gram mirroring
between isolated downstreams is in the same signal class as SENTINEL's
published 4-gram overlap. Implementation details beyond the class
description in this repository are not included here. Where we report
values computed with Gagne's published definition of 4-gram overlap, we
use his definition directly; where we report values computed with an
internal measure in the same signal class, we state that distinction
explicitly.
