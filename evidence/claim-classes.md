# Claim Classes

*Every claim in this release is tagged as one of the following four
classes. This document defines the tags; the review responsibility is
to keep every assertion correctly classified.*

## Class definitions

### source-backed

A claim directly supported by a published, verifiable artifact — the
SENTINEL v1 or v2 release, the pre-registered secondary analysis, or
a peer-reviewed reference.

**Standard of evidence:** a competent reader can reproduce the claim
from public materials.

### analytic-inference

A claim logically derived from source-backed claims but not itself a
direct observation. Extensions, interpretations, implications.

**Standard of evidence:** the derivation is explicit, the source
claims are cited, and the inference step is visible.

### held

A claim that depends on detection-engine internals not disclosed in
this release. Such claims do not appear in the public text; they may
appear internally as supporting context for analytic-inference
claims.

**Standard of evidence:** internal; not published.

### preliminary

A claim that is empirically observed but not yet pre-registered. May
be reported as preliminary with explicit status disclosure.

**Standard of evidence:** the observation is reported; the
pre-registration status is declared at the point of claim.

## Classification of the principal claims

| Claim | Class |
|---|---|
| SENTINEL v2's 23-experiment pre-registered result: Tier A prediction FAIL, Tier B detection PASS | source-backed |
| Substrate-shaped interpretation — the failure is a property of the baseline-establishment window, not apparatus capability | analytic-inference |
| SENTINEL v2's accidental-governance thesis (probes suppressed drift 3–6x via context-window anchoring) | source-backed (Gagne v2) |
| T2 fan-out sibling pair measured S4 = 0.366 across 31 windows despite no direct sibling dialogue channel | preliminary |
| Typed-intent repair as the architected analogue of SENTINEL v2's accidental mechanism | analytic-inference |
| Under the repair pattern, free-text inter-agent payloads are inadmissible at the exchange boundary | analytic-inference |
| Shared-broker fan-out is a real A2A coupling surface | analytic-inference from the measured T2 sibling-coupling result |
| Chatty agent cards as pre-coupling substrate | analytic-inference derived from indirect-coupling reasoning, not claimed here as the directly measured mechanism |
| Vaccine-stack efficacy in general deployment | analytic-inference; independent validation is future work |

## Review discipline

- Every assertion in the publication-surface files carries an
  implicit or explicit class tag.
- Upgrading a preliminary claim to source-backed requires a
  corresponding pre-registration to appear first.
- A held claim never appears in publication-surface text. If an
  argument requires one, the argument is reformulated to rest on
  analytic-inference from source-backed claims only.
- Cross-reference: the prevention-vs-detection split governs what can
  appear. See [README.md](../README.md) and
  [methods/signal-class-description.md](../methods/signal-class-description.md).
