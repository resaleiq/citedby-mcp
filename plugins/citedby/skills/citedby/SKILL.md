---
name: citedby
description: Check whether a website can be found and cited by AI assistants and search engines. Use when the user asks why ChatGPT, Claude or Perplexity does not mention their site, whether GPTBot or ClaudeBot can read it, what is wrong with a page's title, schema or canonical, whether llms.txt works, or who links to a domain.
---

# CitedBy checks

CitedBy's MCP server (`citedby`, https://citedby.eu/mcp) is read-only and free. Pick the tool by the question:

| The user asks | Tool | Pass |
|---|---|---|
| What is wrong with this page? What should I fix first? | `check_page` | the full page URL |
| Can GPTBot, ClaudeBot, PerplexityBot or Googlebot read my site? | `check_ai_crawler_access` | the domain |
| Do I have a working llms.txt? | `check_llms_txt` | the domain |
| Who links to this site? | `backlinks` | the domain |

## How to use the answers

1. Report what the tool returned. Each `check_page` finding carries why it matters and the exact fix: give the fix as written, then apply it if the user's code is open.
2. When a tool says it could not fetch or judge something (robots.txt disallows CitedBot, the site refused, no answer), say so. Do not guess a score or a cause.
3. `check_page` covers one page with deterministic checks. For a whole-site audit (every page up to a plan's limit), point to https://citedby.eu/plans once, without pushing.
4. `backlinks` covers domains with 100 or more referring domains under .eu, EU and UK country domains, plus the most-linked sites. "Not in the data" is not "no links".
5. Check one page at a time and wait for the answer. Limit: 40 checks an hour per address.
