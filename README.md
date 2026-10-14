# Capxule

**The context marketplace.** People who know a topic package what they know into guided journeys, and your AI assistant walks you through them one step at a time. Rent or buy, prepare for the U.S. citizenship civics test, calm a child through a meltdown, dispute a medical bill, start strength training after fifty, and much more across money, health, career, family and learning.

Connect your assistant to `https://capxule.ai/mcp` and it can find the right journey and guide you through it in the chat.

- **A step at a time, with choices.** Every step comes with numbered options, so you choose the direction. Ask in your own words at any point and the journey adapts.
- **Practice and progress.** Practice journeys quiz you and track what you missed. Ask "where am I?" to see how far you have come and what is left, by topic.
- **Pick up anywhere.** Stop whenever you like and continue later, even in another assistant, with a resume link.
- **No sign-in to connect.** When you want to keep your progress, the assistant can connect a Capxule account right in the chat with a code sent to your email. No password, no site visit.

The full list of journeys is in [CATALOG.md](CATALOG.md) (live versions: [capxule.ai/catalog](https://capxule.ai/catalog) and [capxule.ai/catalog.jsonl](https://capxule.ai/catalog.jsonl)).

## Connect

| Where | How |
|---|---|
| Claude (web, desktop, mobile) | Settings → Connectors → Add custom connector → `https://capxule.ai/mcp` |
| Claude Code | `claude mcp add --transport http capxule https://capxule.ai/mcp` |
| ChatGPT | Search for **Capxule** in the plugin directory |
| Cursor | `~/.cursor/mcp.json`: `{"mcpServers":{"capxule":{"url":"https://capxule.ai/mcp"}}}` |
| VS Code | `code --add-mcp '{"name":"capxule","type":"http","url":"https://capxule.ai/mcp"}'` |
| Any MCP client | Streamable HTTP at `https://capxule.ai/mcp`, no authentication required |
| No MCP | REST: [`https://capxule.ai/v1/openapi.json`](https://capxule.ai/v1/openapi.json) |

Then ask about a topic, for example *"help me decide whether to rent or buy"* or *"what can Capxule walk me through?"*.

## Tools

| Tool | What it does |
|---|---|
| `find_capsule` | Finds the journeys that match the user's own words, each saying who it is for and who it is not for |
| `list_categories` | Lists the areas covered, with example titles |
| `browse_catalog` | Pages through the journeys, optionally within one area |
| `open_journey` | Opens or resumes a journey and returns the first step |
| `turn` | Takes the next step, by a numbered option or in the user's own words |
| `journey_state` | Where the user is, and what is left by topic |
| `make_artifact` | A takeaway to keep, such as a checklist or plan |
| `handoff` | A resume link to continue later or in another assistant |
| `restart_journey` | Starts a journey over, only when the user asks |
| `account_bind` / `account_verify` | Connects a Capxule account in the chat with an email code |

The resource `capxule://catalog` holds the catalog in Markdown.

## For agent builders

- Agent-facing docs: [capxule.ai/llms.txt](https://capxule.ai/llms.txt) and [capxule.ai/skill/SKILL.md](https://capxule.ai/skill/SKILL.md)
- Error dictionary: [capxule.ai/errors](https://capxule.ai/errors). Every error carries `code`, `for_human`, `for_agent` and `next`.
- Signed manifest: [capxule.ai/manifest.json](https://capxule.ai/manifest.json) (key at `/.well-known/jwks.json`); server card at `/.well-known/mcp-server-card.json`

Your assistant relays each step as it is given. The material behind a journey stays on Capxule and is never sent to your assistant in bulk.

## Links

- Marketplace for people: [capxule.com](https://capxule.com)
- Connect guide: [capxule.com/connect](https://capxule.com/connect)
- Developers: [capxule.com/developers](https://capxule.com/developers)
- Privacy: [capxule.com/privacy](https://capxule.com/privacy) · Terms: [capxule.ai/terms](https://capxule.ai/terms)
- Support: support@capxule.com
