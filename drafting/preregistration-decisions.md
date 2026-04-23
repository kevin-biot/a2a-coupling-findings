# Pre-registration Decisions (drafting-only)

*Internal notes on pre-registration status per finding. The
publication-surface pre-registration manifest lives at
[preregistration/README.md](../preregistration/README.md) and contains
only what is public-grade.*

## Finding 1 — SENTINEL v2 secondary analysis

**Status:** pre-registered.

- Protocol: internal record (private ADR corpus).
- Pre-registration SHA-256:
  `723487bf66e414200891ae938de887b818675a5c0dc8c1e7ed8078b9c451eb55`
- Commit date: 2026-04-19, prior to first execution of the evaluation
  script against SENTINEL v2's ground-truth timings.
- Amendments: three, all committed prior to execution (see T4 in
  [TODOS.md](./TODOS.md)).

Public manifest: [preregistration/README.md](../preregistration/README.md).

## Finding 2 — Isolated-downstream adaptation

**Status:** not pre-registered (pending decision; see T2 in
[TODOS.md](./TODOS.md)).

### Option A — Pre-register, re-run, publish with full rigour

1. Draft a formal protocol for the isolated-downstream measurement
   (4-gram overlap relative to SENTINEL v2's 14–18% baseline,
   including the specific hub and card-layer configuration).
2. Commit the protocol and its SHA-256 to the publication-surface
   `preregistration/` folder before any measurement run.
3. Execute the measurement once.
4. Publish the finding with full pre-registration discipline matching
   Finding 1.

Cost: additional engineering cycle. Benefit: finding rests on matched
rigour.

### Option B — Publish as preliminary, invite replication

1. Publish the isolated-downstream observation as a preliminary
   finding with explicit "not pre-registered" disclosure.
2. Include a committed protocol for third-party replication.
3. Accept reduced rigour claim relative to Finding 1.

Cost: finding lands at lower evidentiary tier. Benefit: faster release;
headline rests on Finding 1.

## Recommendation

Option A if the isolated-downstream number is the headline. Option B
if Finding 1 carries the paper and Finding 2 is motivating context.
