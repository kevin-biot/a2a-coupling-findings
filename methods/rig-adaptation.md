# Rig Adaptation

## What we reused without modification

- SENTINEL v2's experimental harness as an agent-driver and
  conversation-substrate simulator (Apache 2.0, v2.0.0).
- The SENTINEL v2 release corpus (23 distributed experiments) as input
  data for the pre-registered secondary analysis.
- The experimental-condition categorisation and ground-truth timing
  annotations from the published release.
- SENTINEL v2's hub-and-spoke hardware layout and configuration
  discipline.

## What we adapted

1. **Agent-connectivity layer.** SENTINEL v2 runs hub-and-spoke
   hardware with full-mesh agent connectivity (every agent observes
   every other agent's dialogue). We modified the agent-connectivity
   layer to isolated downstreams: two downstream agents with no
   direct visibility of each other's messages, separated by an
   upstream routing hub. Hardware topology is unchanged. See
   [hub-spoke-vs-mesh.md](./hub-spoke-vs-mesh.md).
2. **Capability-advertisement layer.** We added an agent-card
   registration phase in which each downstream agent publishes a
   natural-language capability description consumed by the upstream
   hub during routing. This is a standard pattern in production A2A
   deployments and is the mechanism whose risk profile we sought to
   test. It is not present in SENTINEL's published configurations.
3. **Analysis layer.** A separate drift-detection apparatus was
   connected as an independent observer. The apparatus has no
   control authority; it consumes the rig's output stream and emits
   class-level signals. The apparatus internals are not published in
   this release.

## What we did not do

- We did not modify agent behaviours inside SENTINEL's rig. Persona
  definitions, turn generation, and conversational substrate
  simulation are unchanged.
- We did not alter the ground-truth timing annotations used for the
  pre-registered evaluation.
- We did not reimplement SENTINEL's signal vocabulary. Our class-level
  signal descriptions (see
  [signal-class-description.md](./signal-class-description.md)) share
  terminology with SENTINEL where appropriate (notably G5 and the
  4-gram overlap class) and acknowledge the lineage. Where we report
  values against SENTINEL's named signals (e.g., 4-gram overlap
  against the 14–18% isolated baseline), we use SENTINEL's definition
  directly, not a re-derivation.

## Reproducibility path

- Pre-registered protocol and SHA — see
  [preregistration/](../preregistration/).
- Corpus identity — SENTINEL v2 release, as recorded in
  [ATTRIBUTION.md](../ATTRIBUTION.md).
- Agent-connectivity-layer adaptation specification — this document
  plus [hub-spoke-vs-mesh.md](./hub-spoke-vs-mesh.md).
- Class-level signal descriptions —
  [signal-class-description.md](./signal-class-description.md).

A third party wishing to reproduce the finding can:

- Replicate with SENTINEL's published rig plus an independent choice
  of detection apparatus at the class level described here; or
- Replicate the structural observation (indirect coupling between
  isolated downstream agents via hub and card layer) using any
  suitable harness and any implementation of the published 4-gram
  overlap measure.

The finding — that isolated downstream agents couple via the hub and
agent-card pathways — does not depend on the specific detection
engine. Any implementation of the signal class described should
observe the same qualitative pattern.
