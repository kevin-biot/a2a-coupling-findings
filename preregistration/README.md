# Pre-registration Anchor

*Reproducibility manifest for the pre-registered supporting SENTINEL
re-analysis reported in [results/](../results/).*

## Pre-registration

- **Protocol:** committed to version control prior to execution of the
  evaluation script against ground-truth timings. No retrospective
  changes to pass criteria, signal definitions, or evaluation
  procedure.
- **Pre-registration SHA-256:**
  `723487bf66e414200891ae938de887b818675a5c0dc8c1e7ed8078b9c451eb55`
- **Commit date:** 2026-04-19, prior to first execution of the
  evaluation script.
- **Amendment discipline:** three amendments were committed prior to
  execution; each was SHA-anchored before any evaluation run. The
  amendment log is available on request for independent review.

## Evaluation

- The evaluation script was executed once against the ground-truth
  timings of SENTINEL v2's 23-experiment release.
- The pre-registration SHA-256 was re-verified at run time and logged
  in the evaluation output.
- The verdict was computed per the pre-registered criteria. Results are
  reported in [results/phase-b-summary.md](../results/phase-b-summary.md),
  the supporting SENTINEL re-analysis.

## Scope

This pre-registration applies to the supporting SENTINEL re-analysis
only. The current primary A2A finding in this repository is the
preliminary T2 fan-out measurement described in
[results/a2a-findings.md](../results/a2a-findings.md); it is not covered
by this pre-registration. The stricter isolated-downstream replication
line described in [methods/hub-spoke-vs-mesh.md](../methods/hub-spoke-vs-mesh.md)
is separate work and carries its own future pre-registration
discipline.

## Reproducibility without detection-engine disclosure

A third party can verify the discipline without access to the
detection engine:

1. The pre-registration SHA-256 is reproducible from any copy of the
   pre-registration file. A copy will be vendored into the public
   release at publication time.
2. The evaluation script is not published in this release. A
   class-level description of what it computes is in
   [methods/signal-class-description.md](../methods/signal-class-description.md).
3. The finding — that a generic-apparatus prediction claim fails on
   rapid-collapse substrate while an n-gram-mirroring detection
   claim holds — does not depend on the specific engine. Any
   implementation of the signal class described should produce the
   same verdict class on the same corpus.

## What this anchor does not do

- It does not publish the detection-engine internals.
- It does not substitute for a cryptographic timestamp. An
  OpenTimestamps anchor will be added at public release if stronger
  third-party verification is required.
