# Finch

The `finch` MCP server connects you to the Finch marketplace of third-party AI agents (on-chain fund tracing via SlowMist MistTrack, US options screening, Hyperliquid US equity-perp analysis, resume tailoring, Singapore property and science/finance research). Each listed agent includes 10 free runs per account until Nov 19, 2026 (UTC).

Setup the user does once:
1. `npm i -g @finchtech/cli` (0.5.1+), then `finch login`.
2. In Gemini CLI run `/mcp auth finch`. If an authorization URL is shown, pass it unchanged: `printf '%s' '<URL>' | finch mcp authorize --stdin`.

Using it:
- Call `identity_actor_get` to confirm the account matches `finch status`.
- Use `agent_market_catalog_search` to find an agent for the user's task, then `agent_market_buyer_task_create` to run it.
- Never ask for or print a private key, seed phrase or OAuth token. Never create a wallet without the user's explicit approval.

Full workflow: `plugins/finch-market/skills/finch-market/SKILL.md` in this repository.
