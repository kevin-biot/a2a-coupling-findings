# Task Plan

This plan resets the repository around one primary objective:

> publish a clean, defensible public repo for the **A2A coupling
> finding**, with DOP retained only as supporting contrast where it
> sharpens interpretation.

## Principles

- **A2A first.** The main reading path must lead with the A2A empirical
  question, method, and result.
- **Measured before inferred.** Measured findings come first; repair
  patterns, standards implications, and companion architecture come
  later.
- **DOP is secondary.** DOP material can stay only if it serves as a
  comparator, not as the headline.
- **Public surface stays narrow.** Companion-framework context and
  speculative extensions must not dominate the repo narrative.

## Workstreams

### 1. Public surface rewrite

- Rewrite `README.md` around the A2A finding.
- Make the primary reading order explicit.
- Remove wording that makes the repo read like a patent placeholder or
  companion-framework bundle instead of a findings repo.

### 2. Results consolidation

- Keep one clear primary results path under `results/`.
- Treat the pre-registered SENTINEL re-analysis as supporting context,
  not the main artifact.
- Keep DOP comparators in secondary position unless they are required
  to interpret the A2A result.

### 3. Methods cleanup

- Keep the A2A topology adaptation front and center.
- Keep signal descriptions only to the extent needed for scientific
  communication and claim-boundary clarity.
- Avoid turning methods docs into a second headline narrative.

### 4. Evidence hygiene

- Preserve explicit claim classes: measured, inferred, preliminary,
  held.
- Make provenance easy to audit.
- Keep attribution strong without letting derivative-work framing
  overwhelm the actual finding.

### 5. Secondary material containment

- Keep `patterns/` as secondary support, not primary evidence.
- Remove internal drafting material from the public repo.
- Remove or rewrite placeholder reference notes and broken local links.

## Immediate Checklist

- [x] Reframe the repo root around A2A-first publication intent.
- [x] Add a repo-level task plan.
- [x] Add directory-level guidance for `results/` and `methods/`.
- [x] Simplify `references/README.md` so it matches what actually ships.
- [x] Promote a primary A2A findings document based on the measured T2
      sibling-coupling result.
- [x] Final pass on coherence, claim boundaries, and link hygiene.
- [x] Remove internal drafting material from the public repo.
- [x] Add a compact definitions surface for reader-facing vocabulary.
- [ ] Decide whether to add the stricter isolated-downstream
      replication line as a separate preliminary note or defer it.

## Definition of “Clean Enough To Publish”

The repo is ready when a new reader can answer these questions within
five minutes:

1. What is the A2A claim?
2. What evidence in this repo is primary versus supporting?
3. What was measured versus inferred?
4. Why is DOP present, and why is it secondary?
5. What would still need to happen before a fuller external release?
