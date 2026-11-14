# Shannon — Changelog

All notable changes to the Shannon skill, newest first. The same history is
kept at the foot of SKILL.md; the repository's commit history is the
line-by-line record.

## v1.3 — 14 Nov 2026

Step 0 refined: asking is permitted where the user wishes to give an answer,
preferably on the system's initiative (the model asks, drawing its questions
from the record). Answers are weighted at the stated tier — self-report is
the least reliable evidence until behaviour confirms it — and derivation
from the record stays primary.

## v1.2 — 14 Nov 2026

- Existing-map adoption: before any build, Shannon looks for an existing
  Shannon map (by its signature — atlas, cluster summaries, cards and a
  build manifest), adopts it, verifies its coverage against the store, and
  refreshes only the delta. Rebuilding a sound map is prohibited; multiple
  copies are treated as copies of one map, with the master named in the
  deployment pack and divergences surfaced, never merged silently.
- The two mapping criteria are named explicitly in Step 0: (1) the market
  criteria — what the field or context treats as a real change (PROPOSED
  until the record confirms them); (2) the owner's criteria — objectives and
  change-definitions revealed in the owner's own record, including chat
  history, with biases exposed by evidence pointers.
- Repository renamed from `shannon` to `Shannon`.

## v1.1 — 11 Nov 2026

Licence changed to the PolyForm Noncommercial License 1.0.0: noncommercial
use is free; any commercial use requires a paid licence from the copyright
holder in advance, no exceptions. The v1.0 dual-licence wording (GPL v3 +
commercial) was withdrawn — anyone who downloaded v1.0 in its brief window
holds the terms it carried.

## v1.0 — 11 Nov 2026

Initial public release: the no-duplication map (abstracts, verbatim keys,
pointers), resolve-first search with typed thesaurus and house-terms
register, Step 0 frame derivation, the position & delta register, the trend
roll-up, the no-map fallback, and the refresh procedure.
