# Signal Class Description

*Class-level descriptions of the signals used to detect and
characterise coupling. The level of detail here is sufficient for
scientific communication and for third-party replication at the signal
class; specific detection-engine parameters are not disclosed.*

## Shared vocabulary with SENTINEL

Where our signal classes correspond to SENTINEL's named signals, we
use SENTINEL's names and credit the lineage. Full SENTINEL signal
catalogue: see [references/gagne-sentinel.md](../references/gagne-sentinel.md).

Relevant SENTINEL signals for this work:

- **G5:** Shannon diversity index over vocabulary and sentiment.
- **4-gram overlap:** published baseline 14–18% for isolated agents,
  80% for fully-connected (group) agents.
- **Composite diversity, probe drift, probe-message divergence, node
  drift asymmetry, response compression, stance collapse:** see the
  referenced catalogue.

## Signals used in this work

### G5 — bounded coherence / diversity measure

Used in the same class-level sense as SENTINEL: a bounded scalar
summarising vocabulary/sentiment diversity against a rolling baseline.
Drops below baseline-relative thresholds indicate divergence.

**Purpose:** collapse classification. The corpus-wide YELLOW crossing
is the canonical event against which detection lead time is measured.

**Relationship to SENTINEL's G5:** same class. Where we state G5
values against SENTINEL's corpus, those values are computed with
SENTINEL's definition; where we state G5 values against our own
configurations, the parameterisation may differ and is noted.

### S1 — coupling-emergence class

A measure of emergent coupling across agent pairs over a lookback
window. Rises indicate that agents are becoming mutually predictive in
ways their independent baselines do not support.

**SENTINEL-adjacent counterpart:** composite diversity and node drift
asymmetry operate in overlapping territory. S1 is not a direct
restatement.

### S2 — Lyapunov-class stability indicator

A stability-function-derived measure drawn from the coupled-dynamics
basis. Class membership: Lyapunov V-function computed over agent
state trajectories.

**SENTINEL-adjacent counterpart:** none direct. SENTINEL does not
publish a Lyapunov-class signal. This class is contributed by the
present work at class level.

**Result on SENTINEL's release:** detection-rate 1.00 on the
23-experiment corpus; mean lag of 11 turns behind G5 YELLOW. On
rapid-collapse substrates, the baseline-establishment requirement
structurally prevents leading. See
[results/phase-b-summary.md](../results/phase-b-summary.md), the
supporting SENTINEL re-analysis.

### S3 — dimensional-collapse class

A measure of effective-dimensionality reduction in the agent
ensemble's joint state space. Triggered when the ensemble's behaviour
collapses to a substantially lower-dimensional manifold than
baseline.

**Documented caveat:** on SENTINEL v2's 50-dimensional TF substrate,
the pre-registered threshold produces degenerate tail-window firings
in 14 of 23 experiments. This is a threshold-calibration issue
specific to this substrate dimensionality, not a claim about the
signal class. Discussed in
[results/phase-b-summary.md](../results/phase-b-summary.md), the
supporting SENTINEL re-analysis.

### S4 — NL-coupling n-gram mirroring class

A measure of mutual n-gram content sharing between agent pairs,
accumulated over a lookback window. Rises indicate that the agents'
output vocabulary is converging in a way their independent baselines
do not support.

**Published result on SENTINEL's release:** precision 1.00, recall
0.91 (21/23) on the collapse cohort; the two misses are the
fastest-collapse conditions where accumulation had not built
sufficient mass.

**SENTINEL-adjacent counterpart:** S4 is in the same class as
SENTINEL's published **4-gram overlap** measure. SENTINEL's published
baselines — 80% group, 14–18% isolated — are the natural reference
points against which our isolated-downstream adaptation's 4-gram
overlap must be stated.

### 4-gram overlap (SENTINEL's measure, cited directly)

We also report raw 4-gram overlap computed per SENTINEL's published
definition for the isolated-downstream configuration. This is not our
signal; it is SENTINEL's signal applied to a new configuration, for
direct comparability with the published 14–18% isolated baseline.

## Scope of disclosure

A competent reader can, from this document:

- Understand what class of mechanism each signal captures.
- Reproduce the qualitative finding with an independent
  implementation of the signal class.
- For signals where our class overlaps SENTINEL's named signal (G5,
  S4 overlapping 4-gram overlap), compare our substrate-level
  verdicts directly against SENTINEL's.

## Prevention-vs-detection publication split

This document describes the detection side at class level. The
prevention side — typed intent + SHACL shape validation + behavioural
constraints — is published in full in
[patterns/intent-first-typed-graph.md](../patterns/intent-first-typed-graph.md)
and in the companion PACT-public ontology release.
