# Drafting Changelog

Internal drafting milestones. The publication-surface changelog lives
at [../CHANGELOG.md](../CHANGELOG.md) and carries only structural
claim-shape changes to the release.

## 2026-04-23

- Scaffold created.
- Attribution aligned against canonical SENTINEL research page:
  Jason Gagne (no accent), SENTINEL (caps), v1
  [10.5281/zenodo.19103616](https://doi.org/10.5281/zenodo.19103616),
  v2 [10.5281/zenodo.19477188](https://doi.org/10.5281/zenodo.19477188)
  (secondary [10.5281/zenodo.19476723](https://doi.org/10.5281/zenodo.19476723)),
  papers CC BY 4.0, code Apache 2.0 (v2.0.0).
- Contribution framing set: our adaptation is at the
  agent-connectivity layer (isolated downstreams), not at the
  hardware layer (v2 already uses hub-and-spoke hardware).
- Repair pattern positioning: typed intent + SHACL + ontology as the
  **architected analogue** of v2's accidental-governance / AI
  Hawthorne effect thesis. Compositional, not competitive.
- v2 anchored as primary; v1 as foundational prior.
- Repo restructured: publication surface at top level (no DOP-###
  references, no internal commit hashes, no inline TODO markers);
  drafting surface at `drafting/` (gates, TODOs, lineage, paper
  outline).
