# Shannon — Your whole second brain, in a fraction of the space.

*Named for Claude E. Shannon: store the surprise — the delta in meaning — and point at the rest.*

**Your whole second brain, in a fraction of the space.** Shannon is fast, small second-brain infrastructure — an agent skill for searching and tracking a large personal or organisational document store. **Fast**, because answers come from a small standing map (~1,500 loaded tokens) instead of a trawl through the store — so the model's context is spent on reasoning, not on loading data. **Small**, because the map is a fraction of the store (first deployment: 854,378 bytes against 7,167,837 bytes of source text) and there is no vector database ballooning past the store it indexes. Originals are fetched singly, only when exact wording matters. The mechanism that makes it possible is a no-duplication abstract map: no embeddings, no vector store, no text database.

## The problem it solves

Conventional "chat with your documents" systems copy your store into chunks and vectors — an index that can rival or exceed the store itself, that silently fails on exact identifiers (case numbers, SKUs, amounts, deadlines), and that cannot tell you what *changed*: only what is *similar*. Shannon takes the other branch of the lineage that runs from Shannon (1948) through rate–distortion theory and MDL: keep a small, standing **abstract map** of the store, and fetch exact wording live, singly, only when a question needs it.

## How it works

- **The map** — three levels: an *atlas* (~5k tokens, loaded whole) → *cluster summaries* → one *card* per source. Each card holds a short abstract (lossy, plain language), the source's **Keys verbatim** (lossless: identifiers, amounts, deadlines), its entities, and a **pointer** to the original. Connections are never stored as edges; they are derived at query time by joining on shared Keys, entities, clusters and dates.
- **The registry** — a dimension table that resolves any fragment (a name, a topic, a figure) to the canonical key the cards join on.
- **The thesaurus** — typed lay↔technical keyword relationships for the field, with sibling terms' distinctions spelled out, so a lay question ("the judge said she can't continue the case") can find documents written in procedural vocabulary.
- **The house-terms register** — the owner's private vocabulary: nicknames, codenames, inside references. AI proposes entries; only the owner confirms them.
- **The position & delta register** — the record of *meaning in motion*: per holder and axis, the current stance, opinion or plan; the **evidential basis** under it; and a dated log of movements — including the movement a text-diff cannot see, where the basis shifts under unchanged wording.
- **The trend roll-up** — the delta log read as a time series: drift, oscillation, reversal, stillness.

## The frame is derived, never asked

A delta exists only under a frame — a stipulation of what counts as a change — and neither mathematics nor the user's self-report can supply it honestly (ask people about their own biases and you receive the free answer). Shannon's Step 0 therefore **derives** the frame from the record of the user's actual behaviour — what they corrected, chased, preserved and let drop — counterweights it with the field's market frame (base rates, signal-versus-noise conventions), and presents it back with its evidence for recognition and correction.

## Two modes

- **Build mode** — card sources into a map, to a fixed card spec; refresh by delta only, additively, never deleting.
- **Search mode** — a nine-step procedure (house terms → resolve → interpret → expand → probe → traverse → drill down → abstain/fall back → answer in the asker's register), with a declared fallback for stores that have no map yet.

## Measured on its first deployment

628 sources, 7,167,837 bytes of source text → a map of 854,378 bytes (11.9%), answering cross-store questions from ~1,500 loaded tokens. The method is domain-free: everything specific — what counts as a Key, the vocabulary, the frame — lives in a private **deployment pack** that is never published with the method.

## Install

Copy `SKILL.md` into your agent's skills directory (Agent Skills format). Then let the skill run its Step 0 against your store.

## Licence — dual licence

Shannon is dual-licensed. **Route 1:** free under the GNU GPL v3.0 (full text in `LICENSE`) — use, modify and redistribute, commercially included, under the GPL's copyleft terms. **Route 2:** if you need to use it outside the GPL's terms (for example in a closed-source product), a paid commercial licence is available from the copyright holder. See `LICENSING.md` for both routes.
