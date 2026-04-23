# Reference: SENTINEL (Gagne, PreneurialWorks research)

**Primary dependency of this work.** Full derivative-work declaration
in [ATTRIBUTION.md](../ATTRIBUTION.md).

## Bibliographic record

- **Author:** Jason Gagne
- **Affiliation:** PreneurialWorks research
- **Framework:** SENTINEL
- **Canonical research page:** https://theallsourceforge.com/research/sentinel.html

### SENTINEL v1

- **Title:** *SENTINEL: Behavioral Drift in Multi-Agent LLM Systems*
- **DOI:** [10.5281/zenodo.19103616](https://doi.org/10.5281/zenodo.19103616)
- **License:** CC BY 4.0
- **Corpus:** 61 experiments, single-node, 15,857 messages, 18,891
  probe measurements.

### SENTINEL v2 (primary anchor of this work)

- **Title:** *Governance Effectiveness in Distributed Multi-Agent LLM
  Systems*
- **DOI (primary):** [10.5281/zenodo.19477188](https://doi.org/10.5281/zenodo.19477188)
- **DOI (secondary):** [10.5281/zenodo.19476723](https://doi.org/10.5281/zenodo.19476723)
- **License:** CC BY 4.0
- **Corpus:** 23 distributed experiments, 20,000+ messages, 58,000+
  probes, 13,800+ calibrations.
- **Topology:** hub-and-spoke hardware across NVIDIA Jetson Orin Nano
  nodes; full-mesh agent connectivity; 10-agent archetypes; 12
  distributed analyzers.

### Code

- **License:** Apache 2.0
- **Tag consumed:** v2.0.0

## What SENTINEL establishes

### v1 foundational findings

- Drift is real and triggered deterministically at macro scale while
  stochastic at micro scale.
- Collapse-triggering conditions catalogued: shuffle, hidden probes,
  token limit.
- Probe-conversation dissociation; hollow verbosity;
  interaction-driven convergence; universal positive conformity;
  macro-deterministic/micro-stochastic patterns.

### v2 central thesis — "Visible Monitoring Is Accidental Governance"

> "Visible Monitoring Is Accidental Governance: Probes suppressed
> drift 3–6x and doubled self-correction."
>
> "The probes were accidentally functioning as governance. Not
> because they enforced anything, but because the
> identity-reinforcement content in the context window acted as a
> behavioral anchor."
>
> "This is the AI Hawthorne effect, quantified. Your compliance
> monitoring isn't just measuring behavior — it's changing it."

This thesis is load-bearing for the present work. It establishes
that anchoring works, and our architectural repair is the
architected analogue of the mechanism SENTINEL v2 identifies as
accidental.

## SENTINEL signal catalogue (verbatim from v2)

| Signal | Definition |
|---|---|
| G5 | Shannon diversity index (vocabulary, sentiment) |
| Composite diversity | Geometric mean of vocabulary, sentiment, stance diversity |
| Probe drift | Flat measurement (delta +0.001 to +0.006) |
| Probe-message divergence | 5–50x gap |
| Node drift asymmetry | 0.60 vs 0.18 |
| Sentiment diversity collapse | −12% to −60% |
| Vocabulary diversity collapse | −23% to −43% |
| Response compression | 0.62x baseline length |
| Stance collapse | −44% |
| 4-gram overlap | 80% (group) vs 14–18% (isolated) |

The 4-gram overlap baseline is directly relevant to the
related isolated-downstream replication line documented in this
repository: SENTINEL's isolated baseline is 14–18%, and remains the
natural external comparison target for any stricter isolated-downstream
A2A replication.

## What this work does with SENTINEL

1. **Pre-registered supporting SENTINEL re-analysis** of the v2
   release — see [results/phase-b-summary.md](../results/phase-b-summary.md).
2. **Preliminary A2A fan-out finding** — see
   [results/a2a-findings.md](../results/a2a-findings.md).
3. **Architectural repair pattern** — typed intent + SHACL +
   behavioural constraints as the architected analogue of v2's
   accidental-governance thesis. See
   [patterns/intent-first-typed-graph.md](../patterns/intent-first-typed-graph.md).

## Citation discipline

v1 and v2 must be cited alongside the present work. SENTINEL first in
any reference block.

## Research Network

Gagne operates a SENTINEL Research Network; participants run worker
agents on local hardware, retain data ownership, and gain access to
aggregated findings. The present work is an external derivative, not
Research Network output.
