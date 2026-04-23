# Pre-registration Lineage (drafting-only)

*Internal mapping between our private ADR corpus and the
publication-surface pre-registration manifest. Never promotes to
public release in this form.*

## Private ADR lineage

- **Parent ADR:** DOP-202 — cross-domain pre-collapse validation gate.
- **Protocol ADR:** DOP-203 — Phase B sharpened protocol, with
  amendments 2026-04-18 (×2) and 2026-04-19 (×1), all prior to
  evaluation.
- **Results ADR:** DOP-204 — Phase B.2 results; Tier A fail, Tier B
  pass; accepted 2026-04-19.

## Artefacts in the private DOP repository

| Artefact | Path |
|---|---|
| Pre-registration file | `research/sentinel-validation/phase-b/pre-registration.json` |
| Evaluation script | `research/sentinel-validation/phase-b/scripts/run_evaluation.py` |
| Per-experiment CSV | `research/sentinel-validation/phase-b/results/per_experiment.csv` |
| Aggregate JSON | `research/sentinel-validation/phase-b/results/aggregate.json` |
| Plots | `research/sentinel-validation/phase-b/results/plots/` |

## Hashes

- Pre-registration SHA-256:
  `723487bf66e414200891ae938de887b818675a5c0dc8c1e7ed8078b9c451eb55`.
- Pre-registration git commit in private DOP repository: `4f0f38e`.

## Mapping from private lineage to public manifest

The publication-surface manifest
([preregistration/README.md](../preregistration/README.md)) reproduces
only the content that is public-grade:

- The pre-registration SHA-256 (verifiable from any copy of the
  protocol file).
- The commit date of the pre-registration (2026-04-19).
- The assertion that three amendments were committed prior to
  execution, with the log available on request.
- A class-level description of what the evaluation script computes.

The publication-surface manifest does **not** reference DOP-### ADR
numbers, the private DOP repository, or the specific file paths
listed above. Those remain internal.

## Before public release

1. Vendor the pre-registration file into the public release so the
   SHA-256 is reproducible by any reviewer without requiring access
   to the private repository. Target location: `preregistration/pre-registration.json`.
2. Produce a public-facing amendment log: date, short description,
   and post-amendment SHA of the protocol file. Short descriptions
   must not leak private ADR identifiers.
3. Optionally, commit an OpenTimestamps proof of the
   pre-registration file hash to strengthen third-party
   verifiability (see N1 in [TODOS.md](./TODOS.md)).
