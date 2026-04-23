# Results — Supporting SENTINEL Re-analysis

*Supporting SENTINEL re-analysis of the 23-experiment v2 release.
Pre-registration anchor and reproducibility manifest in
[preregistration/](../preregistration/).*

This document keeps the inherited **Phase B** label because the
underlying validation sequence had an earlier private **Phase A**
pilot, which ended with an ambiguous go/no-go and triggered the
sharpened pre-registered evaluation reported here. Phase A is not
missing from the research lineage; it is simply not a primary public
artifact of this repository.

This result is **supporting context**, not the primary A2A finding of
the repository. It stays in the public surface because it sharpens the
interpretation of substrate behavior and claim boundaries for the A2A
track.

## Corpus

- Source: SENTINEL v2 release, *Governance Effectiveness in
  Distributed Multi-Agent LLM Systems*, Gagne, PreneurialWorks
  research, CC BY 4.0. DOI
  [10.5281/zenodo.19477188](https://doi.org/10.5281/zenodo.19477188).
- Experiments analysed: 23 of 23.
- Windows per experiment: 100 (except Distributed 10-Agent Baseline:
  40).

## Collapse classification

| Classification | Count |
|---|---|
| Classified as collapse (G5 ≤ 0.85 · baseline) | 23 |
| Classified as non-collapse | 0 |

The pre-registered G5 threshold produced no non-collapse cohort on
this substrate. Every experiment eventually crosses the YELLOW
threshold — a property of SENTINEL's substrate by design, not a
pipeline artifact.

## Tier A — prediction claim (generic apparatus)

| Signal class | Detection rate | Mean lead time (turns) | 95% CI | Verdict |
|---|---|---|---|---|
| S1 (coupling emergence) | 0.83 (19/23) | −36.3 | [−72.1, −9.2] | FAIL |
| S2 (Lyapunov stability) | 1.00 (23/23) | −11.3 | [−18.3, −5.6] | FAIL |
| S3 (dimensional collapse) | 1.00 (23/23) | −175.2 | [−271.3, −86.3] | FAIL |

Negative lead times indicate that the signals **lag** the G5 YELLOW
classification rather than leading it. The pre-registered pass
criterion (mean lead > 0 with 95% CI lower bound > 0) is violated for
all three signals.

S3 detection is degenerate on this substrate — 14 of 23 alerts fire
at the final window, driving the extreme-negative mean. This is a
threshold-calibration artifact for SENTINEL v2's 50-dimensional TF
state space, not a claim about the signal class.

## Tier B — detection claim (NL-coupling specific)

| Metric | Value |
|---|---|
| S4 (n-gram mirroring) cumulative-rise peak mean | 0.158 |
| Precision (collapse) | 1.00 (21/(21+0)) |
| Recall (collapse) | 0.91 (21/23) |
| Verdict against pre-registered criteria | PASS |

The two misses are the fastest-collapse conditions in the corpus,
where the cumulative accumulator had not built sufficient mass. Both
misses occurred on experiments that did collapse; no false positives
are observable on this corpus.

## Structural caveat — empty non-collapse cohort

With `n_non_collapse = 0` on SENTINEL v2's release:

- Tier A false-alarm rate reports zero but is not meaningfully
  constrained (zero denominator).
- Tier B precision of 1.00 is zero-denominator-artefactual in the
  same way.

The verdicts remain valid against the pre-registered criteria — they
evaluate what the criteria evaluate against the data available — but
the interpretive weight of both the Tier A FAIL and the Tier B PASS
is reduced by this structural absence.

## Interpretation

### Why Tier A failed on this substrate

20 of 23 experiments cross G5 YELLOW within the first 3 windows, i.e.
within or before the baseline-establishment window required by
Lyapunov-class detection. The apparatus is structurally unable to
lead a transition that occurs before the apparatus has finished
baselining.

**The apparatus correctly detects collapse; on this substrate it
cannot lead it.** The Tier A failure is substrate-shaped, not
apparatus-refuted.

This is the finding that lets the public claim rest on the substrate
property rather than on unreleased detector details: the substrate
determines the outcome class. Any competent monitor running against a
substrate where collapse emerges inside the baseline window will
produce the same verdict class.

### Why Tier B passed

S4 n-gram mirroring captures a genuine empirical pattern: sustained
small positive elevation of pairwise n-gram overlap accumulates over
short lookbacks, crossing threshold in 21 of 23 collapse experiments.
The signal class detects the NL-coupling failure mode reliably on
this substrate, even where prediction is structurally precluded.

### Why the caveat matters

Until a substrate with both collapse and non-collapse experiments is
analysed, S4's discriminative power against true non-collapse cannot
be separated from its recall on collapse. Further work on substrates
with a meaningful non-collapse cohort is required to constrain this.

## What this finding supports

Supportable claim:

> On a pre-registered analysis of SENTINEL v2's 23-experiment
> release, a generic-apparatus prediction claim fails due to a
> substrate property — collapse emerges inside the
> baseline-establishment window — while a specific
> NL-coupling-detection claim at the n-gram mirroring signal class
> holds with recall 0.91 on the collapse cohort.

Not supportable from this analysis alone:

- Generalisation of the Tier A failure beyond rapid-collapse
  substrates.
- Generalisation of the Tier B pass to substrates with a genuine
  non-collapse cohort.
- Any claim about apparatus superiority; the finding is
  substrate-shaped.
