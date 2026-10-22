# ERC-8004 registration for Finch

`finch-agent-marketplace.json` is an ERC-8004 agent registration file (registration-v1) for the Finch Agent Marketplace.

Register it from a Finch-controlled wallet on the Identity Registry (`0x8004A169FB4a3325136EB29fA0ceB6D2e539a432`, same address on Ethereum, Base and Polygon), for example on Base:

```
cast send 0x8004A169FB4a3325136EB29fA0ceB6D2e539a432 "register(string)" \
  "https://a0971025732-netizen.github.io/finch-agents/erc8004/finch-agent-marketplace.json" \
  --rpc-url https://mainnet.base.org --account <finch-wallet>
```

After registering, add the returned agentId to `registrations` and republish the file.
