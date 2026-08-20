---
description: Answer a MENA legal question with the full grounded workflow (search, reason, graph audit, cite)
---

Research and answer the user's MENA legal question using Dike's grounded pipeline, in this order:

1. **Search** — call `dike_search` with the user's question to find candidate statutes, regulations, or case law. Note the `canonical_id` and `citation_string` of the most relevant results.
2. **Reason** — call `dike_reason` with the question. Every citation in the response has already been checked against the retrieved documents; if `grounding.dropped_unverified_refs` is greater than 0, mention that some claims couldn't be verified and were removed rather than guessed.
3. **Graph audit** — for the primary source(s) the answer relies on, call `dike_graph_traverse` (direction: `both`, edge_types: `amends`, `repeals`) to check whether the provision has since been amended or repealed. If it has, say so explicitly before presenting the answer as current law.
4. **Cite** — if the user references a specific citation string directly, use `dike_cite` to parse and resolve it rather than guessing at the document from memory.

Never state a statute number, article number, or case citation that didn't come back from one of these tool calls. If nothing resolves, say so plainly instead of filling the gap from training data — Dike's whole purpose is verified citations, not plausible-sounding guesses.

Present the final answer with citation strings exactly as returned by the tools, and note explicitly which sources were used.
