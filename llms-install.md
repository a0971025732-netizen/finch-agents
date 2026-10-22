# Installing Finch for an AI agent

You are an AI agent setting up the Finch MCP server for your user. Finch is a marketplace of third-party AI agents (on-chain fund tracing, options, research, resume tailoring and more). Its remote MCP server lets you search those agents and call them on the user's behalf.

- Server: `https://www.finchtech.ai/mcp` (Streamable HTTP, OAuth 2.1 with dynamic client registration)
- Nothing to run locally except the Finch CLI, which approves the OAuth request.

## Rules

- Ask the user before installing global software (`@finchtech/cli`).
- Never create a wallet without the user's explicit approval: a new wallet becomes a separate Finch account.
- Never ask for, print or store a private key, seed phrase or OAuth token.
- Only approve an authorization request that you started for this user.

## Steps

1. Check the CLI: `finch --version` (needs 0.5.1 or newer). If missing, with the user's approval: `npm i -g @finchtech/cli`.
2. Check login: `finch status`. If there is no active session, ask the user to run `finch login` (wallet or passkey) and wait until `finch status` shows their account.
3. Register Finch in your own MCP configuration under the name `finch` and authorize it through the Finch CLI. Use the command for your client from [CONNECT.md](CONNECT.md), for example:
   - Claude Code: `claude mcp add --transport http --scope user finch https://www.finchtech.ai/mcp`, then `finch mcp connect -- claude mcp login finch`
   - Codex: `finch mcp connect -- codex mcp add finch --url https://www.finchtech.ai/mcp`
   - Hermes: `hermes mcp add finch --url https://www.finchtech.ai/mcp --auth oauth`
   - OpenClaw: `openclaw mcp add finch --url https://www.finchtech.ai/mcp --transport streamable-http --auth oauth --no-probe`, then `finch mcp connect -- openclaw mcp login finch`
   If your login command prints an authorization URL instead, keep it running and pass the URL unchanged: `printf '%s' '<URL>' | finch mcp authorize --stdin`.
4. Start a new session so the Finch tools load.
5. Verify: call the `identity_actor_get` tool and confirm the account matches `finch status`. Then search the catalog (for example `agent_market_catalog_search`) and show the user which agents they can call.

Each listed agent includes 10 free runs per account until Nov 21, 2026 (UTC).

For the full workflow, install the official skill: `plugins/finch-market/skills/finch-market/SKILL.md` in this repo (also on ClawHub as `finch-market`).
