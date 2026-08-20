# dike-plugins

Claude Code plugin marketplace for [Dike](https://dike.it.com), grounded MENA
legal search and reasoning over Saudi, Egyptian, and Emirati primary sources.

## Quick start

```
/plugin marketplace add dikeai/plugins
/plugin install dike-legal-search@dike-plugins
```

You'll need a Dike API key (`export DIKE_API_KEY=your-key-here`) unless
you're connecting via Claude.ai/Desktop's OAuth-based Connectors panel
instead. See the plugin's own README for full setup.

## Available plugins

### [dike-legal-search](./dike-legal-search)

Search, cite, and reason over verified Saudi, Egyptian, and Emirati legal
sources via Dike's remote MCP server. Every citation is checked against a
retrieved document before it's returned, unresolved references are dropped,
never guessed.

**Commands**
- `/dike-research` — full grounded workflow: search, reason, graph audit for
  amendments/repeals, and citation verification
- `/dike-search` — browse and compare sources for a topic
- `/dike-cite` — parse and verify a specific citation string

**Tools** (also usable directly, without a slash command)
- `dike_search`, `dike_reason`, `dike_cite`, `dike_graph_traverse`

Requires a Dike API key.

## Updating

Already added the marketplace? Pull the latest plugin versions with:

```
/plugin marketplace update dikeai/plugins
```

## Note on Anthropic's Connectors Directory

This is a self-serve Claude Code plugin marketplace (`/plugin marketplace
add`), anyone can add it, no review required. It is separate from Anthropic's
curated Connectors Directory (browsable in Claude.ai/Desktop's "Partners"
tab), which requires a full OAuth 2.1 authorization flow and Anthropic's
review process. Dike doesn't have that yet; this repo is not affiliated with
or reviewed by Anthropic.
