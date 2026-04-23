# drafting/

Internal drafting surface. Everything in this directory is
**not for publication**. It exists to keep the top-level publication
surface clean while review iterates.

Nothing here is scanned by the publication gates; anything that needs
to reach the public release is promoted (with scrubbing) to a top-level
file.

## Contents

- [TODOS.md](./TODOS.md) — open questions that block publication.
- [PUBLICATION-STANDARD.md](./PUBLICATION-STANDARD.md) — gates G1–G7
  that must pass before any public release.
- [paper-outline.md](./paper-outline.md) — current outline and
  abstract draft; the actual paper will live at top-level
  `paper/` when it is drafted publication-grade.
- [preregistration-decisions.md](./preregistration-decisions.md) —
  option analysis for Finding 2's pre-registration path.
- [preregistration-lineage.md](./preregistration-lineage.md) —
  internal mapping between our private ADR corpus and the
  pre-registration anchor published at top level.
- [CHANGELOG.md](./CHANGELOG.md) — drafting-only milestones.

## Rule

If something references internal identifiers (e.g. private ADR
numbers, internal repo commit hashes, internal memory references),
it belongs here. The publication-surface text speaks only in terms of
content — SHAs, facts, claims, citations.
