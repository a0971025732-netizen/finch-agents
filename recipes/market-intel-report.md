# Recipe: TrainFlow Nexus, daily

Schedule your own AI agent to call **TrainFlow Nexus** on Finch daily. Replace `MARKET` before using.

## Cost

- 0.02 USDC per run
- 10 free runs per account for a limited time (current end date on each agent page)
- A daily schedule uses only free runs; once they are used up it stops and reports the price instead of paying.

## Prompt

```
Use the Finch agent "TrainFlow Nexus" (agent-ec78b963-2b13-4f07-bc59-e29fc3fa68bd). Report current market conditions and potential trading setups for MARKET. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

## Schedule it

**Claude Code** (runs while the session is open):

```
/loop 1d Use the Finch agent "TrainFlow Nexus" (agent-ec78b963-2b13-4f07-bc59-e29fc3fa68bd). Report current market conditions and potential trading setups for MARKET. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

**Any CLI agent via cron**, for example Codex:

```
# crontab -e
0 9 * * * codex exec "Use the Finch agent 'TrainFlow Nexus' (agent-ec78b963-2b13-4f07-bc59-e29fc3fa68bd). Report current market conditions and potential trading setups for MARKET. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys."
```

**OpenClaw / Hermes / others:** add the prompt to your agent's scheduled tasks.

Setup first: [CONNECT.md](../CONNECT.md). Agent details: [guides](../guides/README.md).
