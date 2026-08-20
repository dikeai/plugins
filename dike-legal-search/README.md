# dike-legal-search

Claude Code plugin bundling Dike's remote MCP server: grounded search,
reasoning, citation resolution, and citation-graph traversal over Saudi,
Egyptian, and Emirati primary legal sources.

## Requires

A Dike API key. Get one at https://dike.it.com/developers/ (self-serve signup
is currently closed while in testing; request a key manually until it
reopens, see https://dike.it.com/auth.md).

## Setup

```bash
export DIKE_API_KEY=your-key-here
```

Then, inside Claude Code:

```
/plugin marketplace add dikeai/plugins
/plugin install dike-legal-search@dike-plugins
```

If you're connecting from Claude.ai or Claude Desktop's Connectors panel
instead of Claude Code, click "Connect" on the `dike` connector, it uses
OAuth against your existing Dike account rather than a pasted API key.

## Commands

- `/dike-research` — the full grounded workflow: search, reason, graph audit
  for amendments/repeals, and citation verification, in that order. Use this
  for an actual legal question.
- `/dike-search` — browse and compare sources for a topic without answering
  a question.
- `/dike-cite` — parse and verify a specific citation string against the
  corpus.

## Tools

- `dike_search` — hybrid semantic + lexical search over the corpus
- `dike_reason` — grounded Q&A; every citation is verified against retrieved
  documents before being returned, unresolved references are dropped, never
  guessed
- `dike_cite` — parse and resolve an Arabic citation string to a document
- `dike_graph_traverse` — find documents that cite, amend, repeal, implement,
  or interpret a given document

Same rate limits as the REST API: 60 requests/minute default, 10/minute for
`dike_reason`.

## What this is not

This bundles Dike's existing production MCP server (`api.dike.it.com/mcp`),
it does not run anything locally. There's no separate binary or package to
install beyond this plugin's `.mcp.json` pointer.
