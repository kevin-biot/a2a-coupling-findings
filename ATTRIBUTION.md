# Attribution and Derivative-Work Declaration

## Primary dependency: SENTINEL (Gagne, PreneurialWorks research)

This work is a **derivative extension** of Jason Gagne's SENTINEL
framework for measuring behavioural drift in multi-agent LLM systems.
It anchors to **SENTINEL v2** — *Governance Effectiveness in
Distributed Multi-Agent LLM Systems* — and cites **SENTINEL v1** —
*Behavioral Drift in Multi-Agent LLM Systems* — as foundational prior.
Neither version is replaced or superseded; the present work combines a
pre-registered secondary analysis of v2 with a preliminary A2A fan-out
finding and a related stricter replication line for indirect-coupling
questions.

**Author of primary dependency:** Jason Gagne
**Affiliation:** PreneurialWorks research
**Framework name (verbatim):** SENTINEL
**Canonical research page:** https://theallsourceforge.com/research/sentinel.html

### SENTINEL v1 (foundational prior)

- **Title:** *SENTINEL: Behavioral Drift in Multi-Agent LLM Systems*
- **DOI:** [10.5281/zenodo.19103616](https://doi.org/10.5281/zenodo.19103616)
- **License:** CC BY 4.0
- **Corpus:** 61 experiments, single-node, 15,857 messages, 18,891
  probe measurements.
- **Foundational finding:** behavioural drift in multi-agent LLM
  systems is triggered deterministically at macro scale and stochastic
  at micro scale; collapse-triggering conditions catalogued.

### SENTINEL v2 (primary anchor of this work)

- **Title:** *Governance Effectiveness in Distributed Multi-Agent LLM
  Systems*
- **DOI (primary):** [10.5281/zenodo.19477188](https://doi.org/10.5281/zenodo.19477188)
- **DOI (secondary):** [10.5281/zenodo.19476723](https://doi.org/10.5281/zenodo.19476723)
- **License:** CC BY 4.0
- **Corpus:** 23 distributed experiments, 20,000+ messages, 58,000+
  probes, 13,800+ calibrations.
- **Topology:** hub-and-spoke across NVIDIA Jetson Orin Nano nodes
  with full-mesh agent connectivity; 10-agent archetypes; 12
  distributed analyzers.
- **Central thesis — "Visible Monitoring Is Accidental Governance":**
  probes suppressed drift 3–6x and doubled self-correction, not by
  enforcement but because identity-reinforcement content in the
  context window acted as a behavioural anchor. Named the **AI
  Hawthorne effect**.

### Code release

- **License:** Apache 2.0
- **Tag consumed by this work:** v2.0.0

## What we reused from SENTINEL v2

1. **The experimental harness and configuration discipline.** We
   retained v2's hub-and-spoke hardware layout and 10-agent archetype
   scale, modifying only the agent-connectivity layer (see
   [methods/hub-spoke-vs-mesh.md](./methods/hub-spoke-vs-mesh.md)).
2. **The experimental corpus.** Our secondary analysis consumed 23
   experiments from the SENTINEL v2 release.
3. **The published signal vocabulary at class level.** Terms such as
   G5 (Shannon diversity index), 4-gram overlap, composite diversity,
   probe drift, probe-message divergence, and node drift asymmetry
   originate in SENTINEL and are used here with attribution. Where we
   report values against Gagne's definitions (notably 4-gram overlap
   vs the 14–18% isolated baseline), we use his definition directly.

## What we added

1. **A pre-registered supporting SENTINEL re-analysis** of the
   23-experiment release under an independent protocol, SHA-anchored
   prior to evaluation execution; verdict and methodology in
   [preregistration/](./preregistration/) and [results/](./results/).
   The public repo retains the inherited `phase-b-summary` filename for
   traceability because this analysis followed a private **Phase A**
   pilot in the broader DOP research sequence.
2. **A preliminary A2A fan-out measurement** from the archived DOP T2
   run: sibling specialists with no direct dialogue channel reached
   mean pairwise S4 = 0.366 across 31 windows. See
   [results/a2a-findings.md](./results/a2a-findings.md).
3. **A related stricter replication line** — an isolated-downstream
   adaptation specified as future work at
   [methods/hub-spoke-vs-mesh.md](./methods/hub-spoke-vs-mesh.md).
4. **A structural anti-pattern observation** — free-text capability
   advertisements (agent cards) as a pre-coupling substrate. See
   [patterns/chatty-agent-cards.md](./patterns/chatty-agent-cards.md).
5. **A positive architectural repair pattern** — typed intent over a
   public ontology, validated by SHACL shapes at the A2A exchange
   boundary, composed with bounded behavioural constraints. Framed as
   the **architected analogue** of Gagne's v2 accidental-governance
   finding. See
   [patterns/intent-first-typed-graph.md](./patterns/intent-first-typed-graph.md).

## Relationship to SENTINEL v2's accidental-governance thesis

Gagne's v2 thesis is that probes — out-of-band identity-reinforcement
content in the context window — *accidentally* functioned as
governance by acting as a behavioural anchor. The present work
proposes that the same anchoring mechanism, which Gagne demonstrated
empirically, be **architected** at the A2A exchange boundary rather
than left to incidental probe content: typed intent over public
ontology + SHACL shape validation + bounded action classes.

The two framings compose cleanly:

- SENTINEL v2 establishes that anchoring works.
- This work proposes that anchoring be intentional,
  third-party-verifiable, and failure-closed.

The repair pattern does not claim novelty for typed-interface or
shape-language technologies; it claims novelty for their role as the
architected analogue of Gagne's accidental mechanism, and for the
conformance test it makes possible at the A2A exchange boundary.

## What we do not claim

- We do not reimplement or republish SENTINEL's rig internals. Our
  detection engine is independent and is not published in this
  release.
- We do not replace or supersede SENTINEL v1 or v2. The pre-registered
  verdict *confirms* the substrate property Gagne identified; the
  preliminary A2A finding extends the practical coupling discussion
  without contradicting his result.
- We do not claim novelty for typed-interface, ontology, or
  shape-validation technologies as technologies. We claim novelty for
  their deliberate composition as the vaccine-stack repair for
  SENTINEL-class coupling failure, positioned against Gagne's
  accidental-governance baseline.
- We do not claim generality beyond the analysed substrates now present
  in the repo (SENTINEL v2's release and the archived T2 fan-out A2A
  run). The repair pattern is proposed; independent validation is
  future work.

## Derivative-work statement

This work is a derivative extension of SENTINEL as published by Jason
Gagne at PreneurialWorks research. It is released in the spirit of
reciprocal scientific contribution: our findings strengthen the claim
class Gagne established, and our repair pattern offers an
architectural response compositional with his accidental-governance
insight. Readers citing this work should cite SENTINEL v1 and v2 in
the same reference block.

## Recommended citation order

1. Gagne, J. *SENTINEL: Behavioral Drift in Multi-Agent LLM Systems.*
   PreneurialWorks research, Zenodo. DOI:
   [10.5281/zenodo.19103616](https://doi.org/10.5281/zenodo.19103616).
2. Gagne, J. *Governance Effectiveness in Distributed Multi-Agent LLM
   Systems.* PreneurialWorks research, Zenodo. DOI:
   [10.5281/zenodo.19477188](https://doi.org/10.5281/zenodo.19477188).
3. This work (see [CITATION.cff](./CITATION.cff)).

## Research Network participation

Gagne operates a SENTINEL Research Network in which participants
contribute worker agents and may propose governance conditions to
test. The present work is published as an **external derivative**, not
as Research Network output. Network participation for future
derivative work is a separate decision, not pre-committed by this
release.
