# Publication Standard

## Pre-publication gates

The contents of this repository become public only when **all** of the
following gates are passed:

### G1 — Attribution verified
- [ ] Author name, affiliation, DOI, and release-version in
      [ATTRIBUTION.md](../ATTRIBUTION.md) verified against canonical Zenodo
      record and author's professional profile.
- [ ] License compatibility between our release and Gagne's release
      confirmed.
- [ ] Draft reviewed for any informal mis-spellings or affiliation errors.

### G2 — Claim classes locked
- [ ] Every claim on the public surface (`README.md`, `results/`,
      `methods/`, `patterns/`) is tagged or otherwise handled as one of:
      source-backed, analytic-inference, held.
- [ ] No "held" claim leaks engine internals.
- [ ] No "analytic-inference" claim is phrased as empirical.

### G3 — Pre-registration discipline honoured
- [ ] Phase B.2 pre-registration SHA re-verified against published
      analysis scripts (DOP corpus).
- [ ] Hub-and-spoke finding: either (a) new pre-registration committed to
      this repo and SHA-anchored before publication, or (b) clearly
      declared as preliminary/replication-pending in the paper.
- [ ] Both findings' reproducibility paths are documented even where the
      engine itself is held.

### G4 — Engine held
- [ ] No signal formulas in public text.
- [ ] No threshold values disclosed beyond what is already public in
      Gagne's corpus documentation.
- [ ] No Phase-B golden-input fixtures vendored.
- [ ] Class-level descriptions pass a "would a competent adversary
      reconstruct the engine from this text?" review.

### G5 — Positive repair co-ships
- [ ] At minimum, the intent-first typed-graph-line pattern is a named
      [patterns/](../patterns/) entry with cross-references to PACT-public
      ontology + SHACL shapes (even if those are published separately).
- [ ] The chatty-agent-card anti-pattern is a named
      [patterns/](../patterns/) entry.

### G6 — Companion surfaces ready
- [ ] BRF and GFP are live and reachable at their public URLs.
- [ ] Cross-references between this repo, BRF, and GFP are bidirectional
      where possible.

### G7 — Claim boundaries explicit
- [ ] The "what we do not claim" section of
      [ATTRIBUTION.md](../ATTRIBUTION.md) is honoured by every claim in
      the paper.
- [ ] Scope limits inherited from DOP-202/203/204 are surfaced.
- [ ] "Prediction" vs "detection" distinction is explicit (Tier A FAIL,
      Tier B PASS).

## Publication venue

- Primary: new public GitHub repo, CC-BY-4.0 text, parallel to BRF and GFP.
- Archival: Zenodo snapshot with DOI (matches Gagne's practice).
- Cross-posted only with bidirectional attribution links.

## Revision discipline after publication

- CHANGELOG.md records every structural change to claims or evidence.
- No silent claim rewrites. Superseded claims are marked, not deleted.
- Errata are additive and dated.
