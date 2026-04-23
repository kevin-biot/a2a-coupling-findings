# Open TODOs

Consolidated from drafting. Each TODO is a concrete blocker or
decision required before public release.

## Blockers (must resolve before publication)

### T1 — Measured 4-gram overlap under isolated-downstream configuration

The headline empirical claim of the isolated-downstream finding is a
number against SENTINEL v2's published 14–18% isolated baseline.
Until the measured number lands, the methods section describes the
method and hypothesis; there is no finding.

Owner: Kevin.
Depends on: agreed pre-registration decision (T2).

### T2 — Pre-registration decision for Finding 2 (isolated-downstream)

Two options:

- **Option A:** pre-register protocol for the isolated-downstream
  measurement, commit SHA, run the measurement, publish with full
  pre-registration discipline matching Finding 1 (the SENTINEL v2
  secondary analysis).
- **Option B:** publish the isolated-downstream observation as a
  preliminary finding with explicit "not pre-registered" status; ship
  the protocol for third-party replication; accept reduced rigour
  relative to Finding 1.

Option A is preferred if the isolated-downstream result is the
headline. Option B is acceptable if the headline rests on Finding 1
and the isolated-downstream result is positioned as motivating
context.

Owner: Kevin.

### T3 — Corpus identity of the 23-experiment analysed subset

SENTINEL v2's release is 23 distributed experiments; our
pre-registered analysis used 23 experiments. Likely v2 in full. The
pre-registration protocol records the selection criteria
definitively; extract and state explicitly in
`results/phase-b-summary.md` before publication (currently states the
corpus as "SENTINEL v2's 23-experiment release" on the assumption
that this is correct).

Owner: Kevin.

### T4 — Amendment log for the pre-registered protocol

Three amendments were committed prior to evaluation execution. For
the public release, produce an amendment log with date, short
description, and the SHA of the amended file at each step. Does not
require disclosure of the amendment content beyond what the protocol
itself states.

Owner: Kevin.

### T5 — Attribution record verification pass

Before public release, a single pass through ATTRIBUTION.md,
CITATION.cff, references/gagne-sentinel.md to re-verify author name,
affiliation, titles, DOIs, licenses against the canonical research
page and Zenodo records. Stop if any field has drifted from
canonical.

Owner: Kevin (or delegated reviewer).

## Non-blockers (nice to resolve)

### N1 — OpenTimestamps anchor for the pre-registration SHA

Pre-registration SHA is reproducible from the protocol file. An
OpenTimestamps proof anchored at or before the public release date
would add third-party verifiability without requiring cooperation.

### N2 — Framing references populated

References scaffolding exists for ISS/small-gain, Lotka-Volterra
coupling, a multi-turn drift survey, a coupled-dynamics basis, and a
prompt-injection canonical. Each stub becomes a full reference note
before publication.

### N3 — Companion PACT-public ontology + SHACL shapes release

The architectural repair pattern (intent-first-typed-graph) is more
credible when PACT-public ontology + SHACL shapes are live. Sequencing
TBD; not a blocker for this paper but strengthens the repair claim.

## Known non-issues (for reviewer clarity)

- **Name spelling:** verified Jason Gagne (no accent) against
  canonical research page 2026-04-23.
- **Framework casing:** SENTINEL in caps throughout; verified.
- **License compatibility:** SENTINEL papers CC BY 4.0, code Apache
  2.0; our text CC BY 4.0. No derivative software artefacts in this
  release. Compatible.
