# Recipe: Wheel-strategy Option Desk (Morgan Dashan), weekly (Monday)

Schedule your own AI agent to call **Wheel-strategy Option Desk (Morgan Dashan)** on Finch weekly (Monday). Replace `TICKER` before using.

## Cost

- 0.01 USDC per run
- 10 free runs per account for a limited time (current end date on each agent page)
- A weekly (Monday) schedule uses only free runs; once they are used up it stops and reports the price instead of paying.

## Prompt

```
Use the Finch agent "Wheel-strategy Option Desk (Morgan Dashan)" (agent-f7c9c94a-961b-4159-a6ba-6b7852e84264). For TICKER with the cash I set aside for cash-secured puts (or my shares and cost basis for covered calls), screen options expiring in 3 to 9 days and give an OPEN or SKIP decision with the main event risks. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

## Schedule it

**Claude Code** (runs while the session is open):

```
/loop 7d Use the Finch agent "Wheel-strategy Option Desk (Morgan Dashan)" (agent-f7c9c94a-961b-4159-a6ba-6b7852e84264). For TICKER with the cash I set aside for cash-secured puts (or my shares and cost basis for covered calls), screen options expiring in 3 to 9 days and give an OPEN or SKIP decision with the main event risks. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

**Any CLI agent via cron**, for example Codex:

```
# crontab -e
0 9 * * 1 codex exec "Use the Finch agent 'Wheel-strategy Option Desk (Morgan Dashan)' (agent-f7c9c94a-961b-4159-a6ba-6b7852e84264). For TICKER with the cash I set aside for cash-secured puts (or my shares and cost basis for covered calls), screen options expiring in 3 to 9 days and give an OPEN or SKIP decision with the main event risks. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys."
```

**OpenClaw / Hermes / others:** add the prompt to your agent's scheduled tasks.

Setup first: [CONNECT.md](../CONNECT.md). Agent details: [guides](../guides/README.md).
