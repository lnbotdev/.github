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
$ lnbot pay alice@ln.bot --amount 1000
✓ Sent! Settled instantly
  amount:  1,000 sats
  balance: 46,500 sats
```

**MCP** — give any AI model a Lightning wallet

```json
{
  "mcpServers": {
    "lnbot": {
      "type": "url",
      "url": "https://api.ln.bot/mcp",
      "headers": { "Authorization": "Bearer uk_..." }
    }
  }
}
```

**REST API** — standard HTTP from any language

```
POST /v1/wallets/wal_.../payments
{ "target": "alice@ln.bot", "amount": 1000 }

→ 200 { "number": 1, "status": "settled", "amount": 1000, "actualFee": 0 }
```

---

### `0x02` SDKs

> SDKs that feel native. Pick your language.

#### TypeScript &ensp; [![npm](https://img.shields.io/npm/v/@lnbot/sdk?style=flat-square&color=00ff41&label=npm)](https://www.npmjs.com/package/@lnbot/sdk)

```ts
import { LnBot } from "@lnbot/sdk"

const ln = new LnBot({ apiKey: "uk_..." })
const w = ln.wallet("wal_...")
await w.payments.create({ target: "alice@ln.bot", amount: 1000 })
```

[`typescript-sdk →`](https://github.com/lnbotdev/typescript-sdk)

#### Python &ensp; [![PyPI](https://img.shields.io/pypi/v/lnbot?style=flat-square&color=00ff41&label=pypi)](https://pypi.org/project/lnbot/)

```python
from lnbot import LnBot

ln = LnBot(api_key="uk_...")
w = ln.wallet("wal_...")
w.payments.create(target="alice@ln.bot", amount=1000)
```

[`python-sdk →`](https://github.com/lnbotdev/python-sdk)

#### Go &ensp; [![Go](https://img.shields.io/github/go-mod/go-version/lnbotdev/go-sdk?style=flat-square&color=00ff41&label=go)](https://pkg.go.dev/github.com/lnbotdev/go-sdk)

```go
client := lnbot.New("uk_...")
w := client.Wallet("wal_...")

w.Payments.Create(ctx, &lnbot.CreatePaymentParams{
    Target: "alice@ln.bot",
    Amount: lnbot.Ptr(int64(1000)),
})
```

[`go-sdk →`](https://github.com/lnbotdev/go-sdk)

#### Rust &ensp; [![crates.io](https://img.shields.io/crates/v/lnbot?style=flat-square&color=00ff41&label=crates.io)](https://crates.io/crates/lnbot)

```rust
let client = LnBot::new("uk_...");
let w = client.wallet("wal_...");

w.payments().create(
    &CreatePaymentRequest::new("alice@ln.bot").amount(1000),
).await?;
```

[`rust-sdk →`](https://github.com/lnbotdev/rust-sdk)

#### C# &ensp; [![NuGet](https://img.shields.io/nuget/v/LnBot?style=flat-square&color=00ff41&label=nuget)](https://www.nuget.org/packages/LnBot)

```csharp
var client = new LnBotClient("uk_...");
var w = client.Wallet("wal_...");

await w.Payments.CreateAsync(new() { Target = "alice@ln.bot", Amount = 1000 });
```

[`csharp-sdk →`](https://github.com/lnbotdev/csharp-sdk)

---

### `0x03` WHY LN.BOT

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

**Install the CLI:**

```shell
curl -fsSL https://ln.bot/install.sh | bash
```

**Create a wallet and start using it:**

```shell
lnbot init
lnbot wallet create --name agent01
lnbot invoice create --amount 1000 --memo "first payment"
lnbot balance
```

**Or use an SDK:**

```shell
npm install @lnbot/sdk              # TypeScript
pip install lnbot                    # Python
go get github.com/lnbotdev/go-sdk   # Go
cargo add lnbot                      # Rust
dotnet add package LnBot             # C#
```

Your AI agent now has access to Bitcoin. ⚡

---

[ln.bot](https://ln.bot) · [Docs](https://ln.bot/docs) · [CLI](https://github.com/lnbotdev/cli) · [TypeScript](https://github.com/lnbotdev/typescript-sdk) · [Python](https://github.com/lnbotdev/python-sdk) · [Go](https://github.com/lnbotdev/go-sdk) · [Rust](https://github.com/lnbotdev/rust-sdk) · [C#](https://github.com/lnbotdev/csharp-sdk)

MIT License
