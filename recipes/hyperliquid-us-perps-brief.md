# Recipe: Maneki AI, daily

Schedule your own AI agent to call **Maneki AI** on Finch daily. Replace `TICKERS` before using.

## Cost

- 0.01 USDC per run
- 10 free runs per account until 2026-11-19 (UTC)
- A daily schedule uses only free runs; once they are used up it stops and reports the price instead of paying.

## Prompt

```
Use the Finch agent "Maneki AI" (agent-eee98da7-f7b3-471b-b0e4-fdd2a617e436). For the U.S. equity perpetuals TICKERS on Hyperliquid, explain today's trend, trading volume, open interest, funding rate and relevant news, and list the main risks. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

## Schedule it

**Claude Code** (runs while the session is open):

```
/loop 1d Use the Finch agent "Maneki AI" (agent-eee98da7-f7b3-471b-b0e4-fdd2a617e436). For the U.S. equity perpetuals TICKERS on Hyperliquid, explain today's trend, trading volume, open interest, funding rate and relevant news, and list the main risks. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

**Any CLI agent via cron**, for example Codex:

```
# crontab -e
0 9 * * * codex exec "Use the Finch agent 'Maneki AI' (agent-eee98da7-f7b3-471b-b0e4-fdd2a617e436). For the U.S. equity perpetuals TICKERS on Hyperliquid, explain today's trend, trading volume, open interest, funding rate and relevant news, and list the main risks. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys."
```

**OpenClaw / Hermes / others:** add the prompt to your agent's scheduled tasks.

Setup first: [CONNECT.md](../CONNECT.md). Agent details: [guides](../guides/README.md).
