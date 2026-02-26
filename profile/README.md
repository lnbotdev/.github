```
 ██╗     ███╗   ██╗   ██████╗  ██████╗ ████████╗
 ██║     ████╗  ██║   ██╔══██╗██╔═══██╗╚══██╔══╝
 ██║     ██╔██╗ ██║   ██████╔╝██║   ██║   ██║
 ██║     ██║╚██╗██║   ██╔══██╗██║   ██║   ██║
 ███████╗██║ ╚████║██╗██████╔╝╚██████╔╝   ██║
 ╚══════╝╚═╝  ╚═══╝╚═╝╚═════╝  ╚═════╝    ╚═╝
```

**Bitcoin for AI Agents.**

Give your AI agents access to Bitcoin.
Lightning wallet with CLI, MCP, and API — ready in seconds.

[Website](https://ln.bot) · [Documentation](https://ln.bot/docs) · [Get Started](#0x05--get-started)

---

### `0x01` INTERFACES

> One action. Three protocols. Pay 1,000 sats — through whichever interface fits your stack.

**CLI** — pipe it, script it, cron it

```shell
$ lnbot pay lnbc1...f3q
→ ✓ paid 1,000 sats (fee: 2 sat, 180ms)
```

**MCP** — give any AI model a Lightning wallet

```json
{"tool": "lightning_pay", "amount": 1000}
→ {"status": "paid", "fee": 2, "ms": 180}
```

**REST API** — standard HTTP from any language

```
POST /v1/payments {"bolt11": "lnbc1..."}
→ 200 {"paid": true, "amount": 1000, "fee": 2}
```

---

### `0x02` SDKs

> SDKs that feel native. Pick your language.

#### TypeScript &ensp; [![npm](https://img.shields.io/npm/v/@lnbot/sdk?style=flat-square&color=00ff41&label=npm)](https://www.npmjs.com/package/@lnbot/sdk)

```ts
import { LnBot } from "@lnbot/sdk"

const ln = new LnBot({ apiKey: "key_..." })
await ln.payments.create({ target: "alice@ln.bot", amount: 1000 })
```

[`typescript-sdk →`](https://github.com/lnbotdev/typescript-sdk)

#### Python &ensp; [![PyPI](https://img.shields.io/pypi/v/lnbot?style=flat-square&color=00ff41&label=pypi)](https://pypi.org/project/lnbot/)

```python
from lnbot import LnBot

ln = LnBot(api_key="key_...")
ln.payments.create(target="alice@ln.bot", amount=1000)
```

[`python-sdk →`](https://github.com/lnbotdev/python-sdk)

#### Go &ensp; [![Go](https://img.shields.io/github/go-mod/go-version/lnbotdev/go-sdk?style=flat-square&color=00ff41&label=go)](https://pkg.go.dev/github.com/lnbotdev/go-sdk)

```go
client := lnbot.New("key_...")

client.Payments.Create(ctx, &lnbot.CreatePaymentParams{
    Target: "alice@ln.bot",
    Amount: lnbot.Ptr(int64(1000)),
})
```

[`go-sdk →`](https://github.com/lnbotdev/go-sdk)

#### Rust &ensp; [![crates.io](https://img.shields.io/crates/v/lnbot?style=flat-square&color=00ff41&label=crates.io)](https://crates.io/crates/lnbot)

```rust
let ln = LnBot::new("key_...");

ln.payments().create(
    CreatePaymentParams::new().target("alice@ln.bot").amount(1000),
).await?;
```

[`rust-sdk →`](https://github.com/lnbotdev/rust-sdk)

---

### `0x03` WHY LNBOT

- **Built for agents** — Programmatic wallets, API keys, and idempotent payments designed for autonomous software.
- **Instant settlement** — Payments arrive in seconds, not days.
- **Lightning addresses** — Human-readable addresses like `name@ln.bot`
- **Real-time events** — SSE streams and webhooks for payment notifications.
- **Recovery built in** — 12-word BIP-39 passphrase and passkey backup.
- **Simple pricing** — No monthly fees — pay only when you move sats off-network.

---

### `0x04` PRICING

> No subscriptions. No tiers. Just usage.

```
  ln.bot  →  ln.bot     free
  ln.bot  →  Lightning  0.1% + network fee
  Lightning →  ln.bot   free

  minimum fee: 1 sat
  no monthly fees · no hidden costs · pay only when you move sats off-network
```

---

### `0x05` GET STARTED

```shell
$ npm install @lnbot/sdk     # or: pip install lnbot / go get github.com/lnbotdev/go-sdk
$ lnbot init --network mainnet
$ lnbot serve
```

Your AI agent now has access to Bitcoin. ⚡

---

[ln.bot](https://ln.bot) · [Docs](https://ln.bot/docs) · [TypeScript](https://github.com/lnbotdev/typescript-sdk) · [Python](https://github.com/lnbotdev/python-sdk) · [Go](https://github.com/lnbotdev/go-sdk) · [Rust](https://github.com/lnbotdev/rust-sdk)

MIT License
