# Paper Outline (drafting-only)

*Working outline for the public paper. Once a full draft reaches
publication-grade, it moves to top-level `paper/` and this file is
retired or rewritten as drafting notes.*

## Working title

*Agent-to-Agent Coupling via Indirect Pathways — A Pre-registered
Re-analysis and Isolated-Downstream Extension of the SENTINEL
Framework.*

## Abstract (draft)

Jason Gagne's SENTINEL framework (PreneurialWorks research) established
two substrate-level claims about multi-agent LLM systems in v1
*Behavioral Drift in Multi-Agent LLM Systems* and v2 *Governance
Effectiveness in Distributed Multi-Agent LLM Systems*: that behavioural
drift is deterministic at macro and stochastic at micro scales, and
that visible monitoring probes functioned as **accidental governance**
— suppressing drift 3–6x and doubling self-correction via the AI
Hawthorne effect. We present a pre-registered secondary analysis of
SENTINEL v2's 23-experiment release together with an
agent-connectivity-layer adaptation of v2's rig. On the pre-registered
analysis we find that a generic-apparatus prediction claim fails on
this substrate because collapse emerges inside the apparatus
baseline-establishment window, while an NL-coupling-specific detection
claim at the n-gram mirroring signal class passes with recall 0.91 on
the collapse cohort. Retaining v2's hub-and-spoke hardware layout but
modifying agent connectivity from full-mesh to isolated downstreams,
we ask whether 4-gram overlap between two agents with no direct
dialogue channel exceeds v2's published 14–18% isolated baseline; our
measured value is compared directly. We name the associated
anti-pattern (chatty agent cards as pre-coupling substrate) and propose
an architectural repair — typed intent over public ontology with SHACL
shape validation and behavioural constraints — positioned explicitly
as the **architected analogue** of Gagne's accidental-governance
finding. The result strengthens rather than replaces v2: the substrate
property it identified is not confined to full-mesh agent connectivity,
and the mechanism it identified as accidental can be architected.

## Structure

1. **Introduction** — why this question matters; SENTINEL v1 + v2
   prior work; the gap (connectivity-layer generality; architected
   anchoring).
2. **Related work** — SENTINEL v1 + v2; ISS and coupled-dynamics
   basis; multi-turn LLM drift; prompt-injection literature;
   typed-interface and shape-language prior art.
3. **Method**
   - 3.1 Rig reused — Apache 2.0 v2.0.0.
   - 3.2 Agent-connectivity-layer adaptation.
   - 3.3 Signal classes at class level; engine held.
   - 3.4 Pre-registration discipline.
4. **Results**
   - 4.1 Pre-registered secondary analysis — Tier A FAIL, Tier B PASS.
   - 4.2 Isolated-downstream 4-gram overlap measurement — stated
     directly against v2's 14–18% isolated baseline.
5. **Interpretation**
   - 5.1 Substrate-shaped Tier A failure; permits the engine-held
     stance.
   - 5.2 Indirect coupling via hub + card layer as the
     opposite-polarity sibling of v2's accidental anchoring.
   - 5.3 Implications for production A2A deployments.
6. **Anti-pattern and repair**
   - 6.1 Chatty agent cards as pre-coupling substrate.
   - 6.2 Intent-first typed graph-line A2A as architected anchoring.
   - 6.3 Vaccine-stack composition (ontology + SHACL + behavioural
     constraints).
7. **Scope limits and what we do not claim** — non-mesh and slow-drift
   substrate limits; no claim of apparatus superiority; derivative
   status relative to SENTINEL; no claim of novelty for
   typed-interface technologies.
8. **Reproducibility** — what a third party can reproduce without
   engine access.
9. **Attribution and derivative-work declaration** — v1 + v2 cited;
   compatibility with CC BY 4.0 + Apache 2.0 stated.
10. **References**.

## Drafting conventions

- Match and support Gagne's posture. Class-first, evidence-bounded,
  repair-oriented. Compositional, not competitive.
- Every claim tagged: source-backed / analytic-inference / held /
  preliminary.
- Every number in §4 has a pre-registration pointer or a
  preliminary-status tag.
- Attribution appears in the abstract, §3.1, §5.2, §6.2, and §9.
- SENTINEL in caps throughout.
- Jason Gagne — no accent — throughout.
- The detection-engine-held stance is stated once in §3.3 and
  referenced thereafter.
