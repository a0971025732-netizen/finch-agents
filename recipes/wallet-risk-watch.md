# Recipe: MistTrack (by SlowMist), daily

Schedule your own AI agent to call **MistTrack (by SlowMist)** on Finch daily. Replace `WALLET_ADDRESS` before using.

## Cost

- 0.5 USDC per run
- 10 free runs per account until 2026-11-21 (UTC)
- A daily schedule uses only free runs; once they are used up it stops and reports the price instead of paying.

## Prompt

```
Use the Finch agent "MistTrack (by SlowMist)" (agent-3dcaa57f-b8b8-5c78-9300-c972e5a764bc). Trace recent fund flows for WALLET_ADDRESS, analyze its transaction relationships, and flag any potential risks. Summarize only what changed since the last report. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

## Schedule it

**Claude Code** (runs while the session is open):

```
/loop 1d Use the Finch agent "MistTrack (by SlowMist)" (agent-3dcaa57f-b8b8-5c78-9300-c972e5a764bc). Trace recent fund flows for WALLET_ADDRESS, analyze its transaction relationships, and flag any potential risks. Summarize only what changed since the last report. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys.
```

**Any CLI agent via cron**, for example Codex:

```
# crontab -e
0 9 * * * codex exec "Use the Finch agent 'MistTrack (by SlowMist)' (agent-3dcaa57f-b8b8-5c78-9300-c972e5a764bc). Trace recent fund flows for WALLET_ADDRESS, analyze its transaction relationships, and flag any potential risks. Summarize only what changed since the last report. Rules: use my existing Finch MCP connection (finch-market skill). Only use free runs: if a run would cost money, do not run it, and report the price instead. Never create or switch wallets, and never ask for private keys."
```

**OpenClaw / Hermes / others:** add the prompt to your agent's scheduled tasks.

Setup first: [CONNECT.md](../CONNECT.md). Agent details: [guides](../guides/README.md).
