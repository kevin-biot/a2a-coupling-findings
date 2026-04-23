# Provenance

## External dependencies

SENTINEL framework — Jason Gagne, PreneurialWorks research, Zenodo:

- v1: *SENTINEL: Behavioral Drift in Multi-Agent LLM Systems* —
  DOI [10.5281/zenodo.19103616](https://doi.org/10.5281/zenodo.19103616),
  CC BY 4.0, 61 experiments.
- v2: *Governance Effectiveness in Distributed Multi-Agent LLM
  Systems* — DOI [10.5281/zenodo.19477188](https://doi.org/10.5281/zenodo.19477188)
  (secondary [10.5281/zenodo.19476723](https://doi.org/10.5281/zenodo.19476723)),
  CC BY 4.0, 23 distributed experiments.
- Code release: Apache 2.0, tag v2.0.0.

Upstream A2A application counterpart for the measured fan-out result:

- [kevin-biot/obo-standard](https://github.com/kevin-biot/obo-standard)
- path: `examples/integrations/a2a-multi-hop/`
- concrete agents used for the current measured T2 run:
  `TravelAgent`, `FlightAgent`, `SeatAgent`, `MealAgent`

Upstream ontology counterpart for the DOP-derived repair-pattern line:

- local sibling repo: `ontology`
- local review commit: `b1b57aa`
- public pack/shape companion:
  [kevin-biot/pact-public](https://github.com/kevin-biot/pact-public)
- banking registry family used to ground the DOP-side test surface:
  `registry/banking`, `registry/banking-router`,
  `registry/banking-account-query`, `registry/banking-compliance`,
  `registry/banking-loan-query`, `registry/banking-recurring-payment`

Full attribution: [ATTRIBUTION.md](../ATTRIBUTION.md).

## What we consumed

- SENTINEL v2's 23-experiment release, unmodified.
- Experimental-condition categorisation and ground-truth timing
  annotations from v2.
- SENTINEL's published signal vocabulary (G5, 4-gram overlap,
  composite diversity, probe drift, probe-message divergence, node
  drift asymmetry).
- The OBO A2A multi-hop example topology as the upstream application
  counterpart for the archived T2 run.
- The ontology banking registry family as the concrete bounded-vocabulary
  source for the DOP-side repair-pattern lineage.
- The public PACT pack repo as the reader-facing reference for the
  published shape of ontology packs and SHACL-bound artifacts, distinct
  from the unpublished concrete test packs used in the DOP rig.

## What is in this release

- Pre-registration anchor (SHA-committed prior to evaluation).
- Class-level descriptions of the signals used.
- Results of the pre-registered supporting SENTINEL re-analysis.
- A preliminary measured A2A fan-out finding derived from the archived
  DOP T2 run.
- A stricter related replication line as a method description for the
  indirect-coupling question.
- The typed-intent architectural repair pattern, positioned as the
  architected analogue of SENTINEL v2's accidental-governance
  thesis.

## What is not in this release

- The detection-engine implementation (signal formulas, thresholds,
  classifier internals, accumulation rules).
- Calibration fixtures.
- Any artefact that would allow reconstruction of the held engine.

## Data-integrity

- No input data from SENTINEL's corpus was modified.
- The preliminary A2A fan-out finding is explicitly labelled as a DOP
  archive-derived measurement rather than a SENTINEL result.
- The related isolated-downstream replication line is explicitly
  labelled as this work's adaptation throughout, in
  [ATTRIBUTION.md](../ATTRIBUTION.md), in
  [methods/hub-spoke-vs-mesh.md](../methods/hub-spoke-vs-mesh.md),
  and in the results. It is not reported as a SENTINEL result.
- Numeric values originating in SENTINEL's published release are
  cited to SENTINEL; values originating in the pre-registered
  secondary analysis are cited to the pre-registration anchor; values
  originating in the T2 fan-out finding are identified as archive-
  derived preliminary measurements.
- The public `pact-public` repo is cited as the inspectable reference
  surface for pack structure. It is not claimed to be the exact export
  of the concrete banking test packs used in the DOP comparison rig.

## Compatibility of licensing

- SENTINEL's CC BY 4.0 (papers) is compatible with the CC BY 4.0
  text of this release.
- SENTINEL's Apache 2.0 (code) is compatible with reuse; copyright
  notices and attribution are preserved in any derivative
  configuration.
- No derivative software artefacts are published in this release.
