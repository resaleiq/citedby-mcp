# CitedBy MCP server

Ask your AI tool to check whether a website can be found and cited by AI assistants and search engines. Free, no account, read-only.

Server address: `https://citedby.eu/mcp` (MCP Streamable HTTP, no sign-in). Page with the same instructions: https://citedby.eu/mcp-server

## Tools

| Tool | What you get |
|---|---|
| `check_page` | One page, fetched as [CitedBot](https://citedby.eu/bot) (robots.txt respected): what is wrong for AI answers and search, each finding with why it matters and the exact fix. Deterministic checks only. |
| `check_ai_crawler_access` | For GPTBot, OAI-SearchBot, ChatGPT-User, PerplexityBot, ClaudeBot, Google-Extended, Bingbot and Googlebot: allowed by robots.txt, and answered by the server, or not. |
| `check_llms_txt` | Whether `/llms.txt` exists, whether its links work, whether `/llms-full.txt` exists. |
| `backlinks` | How many domains link to a domain, and the strongest ones, from the Common Crawl web graph. Says when a domain is not in the data. |

When a site refuses the crawler or does not answer, the tool says so. It does not score what it could not read.

## Install

**Claude Code**

```
claude mcp add --transport http citedby https://citedby.eu/mcp
```

or install the plugin, which also adds a skill that picks the right tool for the question:

```
/plugin marketplace add resaleiq/citedby-mcp
/plugin install citedby@citedby
```

**Claude on the web and desktop:** Settings, Connectors, Add custom connector, paste `https://citedby.eu/mcp`.

**Cursor:** [add CitedBy to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=citedby&config=eyJ1cmwiOiJodHRwczovL2NpdGVkYnkuZXUvbWNwIn0=), or add to `~/.cursor/mcp.json`:

```json
{ "mcpServers": { "citedby": { "url": "https://citedby.eu/mcp" } } }
```

**Codex**

```
codex mcp add citedby --url https://citedby.eu/mcp
```

**Any other MCP client:** add a remote server with the address above.

## Ask it like this

- "Check https://example.com/pricing with CitedBy and tell me what to fix first."
- "Can GPTBot and PerplexityBot read example.com?"
- "Does example.com have a working llms.txt?"
- "Which domains link to example.com?"

## Limits

40 checks an hour from one address; a result is reused for up to 6 hours (1 hour for a page check). `check_page` is one page. A whole-site audit, with every page up to your plan's limit and the exact fix for each, is at https://citedby.eu/plans.

Also from CitedBy: [citedby-check](https://github.com/resaleiq/citedby-check), the same AI-crawler check as a command-line tool and GitHub Action.

Questions: hello@citedby.eu. MIT licence.
