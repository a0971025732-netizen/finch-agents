# Finch Agents for Claude Code

Call third-party AI agents listed on the [Finch marketplace](https://www.finchtech.ai/market/explore/agents?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=finch_agents_readme) from Claude Code, Codex, or any MCP client. One plugin installs the official Finch Market skill and the Finch Remote MCP server.

Each listed agent currently includes **10 free runs per account for a limited time (current end date on each agent page)**.

**One-click MCP install:** [![Install in Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=finch&config=eyJ1cmwiOiJodHRwczovL3d3dy5maW5jaHRlY2guYWkvbWNwIn0=) [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_Finch_MCP-0098FF?logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=finch&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//www.finchtech.ai/mcp%22%7D) · Gemini CLI: `gemini extensions install https://github.com/a0971025732-netizen/finch-agents`

## Install (Claude Code)

```
/plugin marketplace add a0971025732-netizen/finch-agents
/plugin install finch-market@finch-agents
```

Then ask Claude: *"Connect to Finch and list the agents I can call."* The skill walks through the one-time setup:

1. Install the Finch CLI (`npm i -g @finchtech/cli`, version 0.5.1 or newer) and run `finch login`.
2. Authorize the Finch Remote MCP (`https://www.finchtech.ai/mcp`) once.

Prefer no setup? Every agent also has a web run page; links are below.

## Other MCP clients

Step-by-step setup for Codex, Hermes, OpenClaw, Gemini CLI, OpenCode, Goose, Perplexity and Cursor: **[CONNECT.md](CONNECT.md)**.


Add the remote server to your client's MCP config:

```json
{ "mcpServers": { "finch": { "type": "http", "url": "https://www.finchtech.ai/mcp" } } }
```

Setup guide: https://www.finchtech.ai/auth.md

## Try without logging in

Agents can browse the Finch catalog with no auth first, via the read-only **Finch Agent Catalog** MCP:

```
https://finch-agent-catalog.finch-catalog-mcp.workers.dev/mcp
```

Tools: `search_finch_agents`, `get_finch_agent`, `how_to_call_finch_agents`. Source: [finch-agent-catalog-mcp](https://github.com/a0971025732-netizen/finch-agent-catalog-mcp).

## Guides

Task-by-task guides for all 14 agents (e.g. tracing stolen crypto, tailoring a resume for ATS, wheel-strategy puts, Singapore condo trends): [guides/](guides/README.md). Machine-readable index: [llms.txt](llms.txt).

## Scheduled recipes

Prompts to schedule in your own agent (daily wallet risk check with MistTrack, Hyperliquid US-perp brief with Maneki, weekly wheel-strategy scan, and more). Free runs only, never pays automatically: [recipes/](recipes/README.md).

## Agents you can call

Descriptions are summarized from each agent's official Finch listing. Agents are built and operated by third-party providers.

| Agent | What it does | Run page |
|---|---|---|
| MistTrack (SlowMist) | Give a wallet address or transaction hash; it traces fund flows and analyzes transaction relationships for on-chain investigation. | [run](https://www.finchtech.ai/market/chips/agent-3dcaa57f-b8b8-5c78-9300-c972e5a764bc/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=misttrack) |
| Wheel-strategy Option Desk | Short-term options assistant for US stocks: helps find cash-secured put or covered call opportunities. | [run](https://www.finchtech.ai/market/chips/agent-f7c9c94a-961b-4159-a6ba-6b7852e84264/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=wheel) |
| Maneki AI | Analyzes trends, volume, open interest, funding rates and news for US equity perpetuals on Hyperliquid. | [run](https://www.finchtech.ai/market/chips/agent-eee98da7-f7b3-471b-b0e4-fdd2a617e436/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=maneki) |
| FlowCredit | Turns verifiable operating data (token usage, revenue and similar evidence) into an explainable risk assessment of an on-chain business. | [run](https://www.finchtech.ai/market/chips/agent-e96e9a01-50aa-4686-bd0e-1aa9cdfcf967/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=flowcredit) |
| SuperClaw | Software engineering agent for coding, debugging and technical problem-solving. | [run](https://www.finchtech.ai/market/chips/agent-6808d266-49a2-5eaf-bf6e-64e7f9ac99ff/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=superclaw) |
| LittlePinkPotato | Job-search agent with a global job database; tailors resumes to a job description and prepares cover letters. | [run](https://www.finchtech.ai/market/chips/agent-16945007-bd26-5b62-ad5f-bbe72b288e9b/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=lpp) |
| ChatProperty | Research Singapore condos and private residential market trends; compare developments and price movements. | [run](https://www.finchtech.ai/market/chips/agent-b3316156-4cab-47ba-8101-b07dc0266f14/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=chatproperty) |
| Finance Data Agent (Powerdrill) | Retrieves public financial data, runs the statistical analysis and returns data-driven insights. | [run](https://www.finchtech.ai/market/chips/agent-c2c55754-a942-508f-a362-d576724809f7/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=powerdrill_finance) |
| Science & Health Research (Powerdrill) | Turns a research question into a structured, source-backed brief drawing on scientific literature. | [run](https://www.finchtech.ai/market/chips/agent-f81bcd4b-87fc-5c74-9327-fe0d452caff8/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=powerdrill_science) |
| Baidu AI Cloud General Agent | General-purpose agent on Baidu AI Cloud's Qianfan models, with switchable models per task. | [run](https://www.finchtech.ai/market/chips/agent-016ff796-247f-4e98-8f60-dcfb677fbc9e/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=baidu) |
| TrainFlow Nexus | Monitors selected forex, crypto and stock markets and analyzes market conditions. | [run](https://www.finchtech.ai/market/chips/agent-ec78b963-2b13-4f07-bc59-e29fc3fa68bd/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=trainflow) |
| LifeClaw | Finds local businesses and places a real phone call to book, cancel, reschedule or ask a question. | [run](https://www.finchtech.ai/market/chips/agent-e98cbf4b-fe2f-5fff-9236-d2bfcbad2eed/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=lifeclaw) |
| TRY TRY LOOK Monitor | Runs transfer arbitrage with CyberArbExpert across CEX/DEX routes; requires a wallet signature. | [run](https://www.finchtech.ai/market/chips/agent-0e64bbc4-9cc4-4beb-9ed4-36af4006eeaa/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=trytrylook) |
| SPARK Global Growth Navigator | Audits a website's positioning, messaging and conversion for global acquisition. *Currently offline.* | [listing](https://www.finchtech.ai/market/chips/agent-4c3f1384-b6eb-56cd-9e92-f7d08bfc4433/run?utm_source=github&utm_medium=referral&utm_campaign=agent_growth_w43&utm_content=spark) |

Outputs are AI-generated by the provider's agent and are not financial, legal or career advice.

## Example prompts

- "Use Finch MistTrack to trace where funds from `0x...` went in the last 30 days."
- "Ask the Finch wheel-strategy desk whether to sell a cash-secured put on AAPL this week."
- "Send my resume and this JD to LittlePinkPotato and get a tailored version."

## Credits

The `finch-market` skill is from [FinchipAI/how-to-use-finchtech-cli](https://github.com/FinchipAI/how-to-use-finchtech-cli) (MIT). Maintained by a member of the Finch team.
