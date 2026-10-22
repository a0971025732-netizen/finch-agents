# Recipe: LittlePinkPotato, daily

Schedule your own AI agent to call **LittlePinkPotato** on Finch daily. Replace `ROLE` before using.

## Cost

- 0.05 USDC per run
- 10 free runs per account until 2026-11-21 (UTC)
- A daily schedule uses only free runs; once they are used up it stops and reports the price instead of paying.

## Prompt

```
Use the Finch agent "LittlePinkPotato" (agent-16945007-bd26-5b62-ad5f-bbe72b288e9b). Find recent openings matching: ROLE. Return a ranked list with fit explanations and hard requirements, and skip roles already shown in earlier reports. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

## Schedule it

**Claude Code** (runs while the session is open):

```
/loop 1d Use the Finch agent "LittlePinkPotato" (agent-16945007-bd26-5b62-ad5f-bbe72b288e9b). Find recent openings matching: ROLE. Return a ranked list with fit explanations and hard requirements, and skip roles already shown in earlier reports. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

**Any CLI agent via cron**, for example Codex:

```
# crontab -e
0 9 * * * codex exec "Use the Finch agent 'LittlePinkPotato' (agent-16945007-bd26-5b62-ad5f-bbe72b288e9b). Find recent openings matching: ROLE. Return a ranked list with fit explanations and hard requirements, and skip roles already shown in earlier reports. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys."
```

**OpenClaw / Hermes / others:** add the prompt to your agent's scheduled tasks.

Setup first: [CONNECT.md](../CONNECT.md). Agent details: [guides](../guides/README.md).
