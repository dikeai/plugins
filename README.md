# dike-plugins

Claude Code plugin marketplace for [Dike](https://dike.it.com), grounded MENA
legal search and reasoning.

## Add this marketplace

```
/plugin marketplace add dikeai/plugins
```

## Available plugins

- **[dike-legal-search](./dike-legal-search)** — search, cite, and reason
  over verified Saudi, Egyptian, and Emirati legal sources via Dike's remote
  MCP server. Requires a Dike API key.

## Note on Anthropic's Connectors Directory

This is a self-serve Claude Code plugin marketplace (`/plugin marketplace
add`), anyone can add it, no review required. It is separate from Anthropic's
curated Connectors Directory (browsable in Claude.ai/Desktop's "Partners"
tab), which requires a full OAuth 2.1 authorization flow and Anthropic's
review process. Dike doesn't have that yet; this repo is not affiliated with
or reviewed by Anthropic.
