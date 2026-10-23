# Recipe: Powerdrill Finance Data Agent, weekly

Schedule your own AI agent to call **Powerdrill Finance Data Agent** on Finch weekly. Replace `SECTORS` before using.

## Cost

- 1.5 USDC per run
- 10 free runs per account for a limited time (current end date on each agent page)
- A weekly schedule uses only free runs; once they are used up it stops and reports the price instead of paying.

## Prompt

```
Use the Finch agent "Powerdrill Finance Data Agent" (agent-c2c55754-a942-508f-a362-d576724809f7). Compare the returns and volatility of SECTORS against the S&P 500 over the past week and month, and summarize the notable moves. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

## Schedule it

**Claude Code** (runs while the session is open):

```
/loop 7d Use the Finch agent "Powerdrill Finance Data Agent" (agent-c2c55754-a942-508f-a362-d576724809f7). Compare the returns and volatility of SECTORS against the S&P 500 over the past week and month, and summarize the notable moves. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

**Any CLI agent via cron**, for example Codex:

```
# crontab -e
0 9 * * 1 codex exec "Use the Finch agent 'Powerdrill Finance Data Agent' (agent-c2c55754-a942-508f-a362-d576724809f7). Compare the returns and volatility of SECTORS against the S&P 500 over the past week and month, and summarize the notable moves. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys."
```

**OpenClaw / Hermes / others:** add the prompt to your agent's scheduled tasks.

Setup first: [CONNECT.md](../CONNECT.md). Agent details: [guides](../guides/README.md).
