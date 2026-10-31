# LockAutopsy

Read-only on-chain check for token locks and vesting contracts — Sablier, Hedgey, UNCX, Team Finance, PinkLock, Streamflow — on Base, Ethereum, Arbitrum, BNB Chain and Solana.

It shows which locks can be cancelled, revoked or transferred. No account, no wallet connection, nothing to sign.

**[Run a free check →](https://lock-autopsy.smither.workers.dev/)**

## What a report tells you

- which supported lock contracts hold this token
- whether each one exposes a setting that can cancel, revoke or transfer the position
- a link to verify every finding yourself on the block explorer

## What it cannot tell you

Coverage is partial: only configured lockers and bounded indexer samples are checked. Unlisted contracts, indexer lag and unverified flags can hide positions, so an empty or clean result is **not** proof that a token is safe. It is a lead to verify, never a safety verdict, and not financial advice.

## Pro

One payment of 19 USDC on Base, no account. Adds per-stream detail and a copyable investigation brief when the sampled data supports it. [Details and price](https://lock-autopsy.smither.workers.dev/pro). Every check still runs on the hosted service — nothing is audited on your machine.

## Elsewhere

- Command line and MCP client: [npm](https://www.npmjs.com/package/lock-autopsy)
- Userscript for DexScreener, GeckoTerminal and GMGN: [GreasyFork](https://greasyfork.org/en/scripts/602782-lockautopsy-on-chain-token-vesting-lock-cancelability-auditor)
- Firefox add-on: [addons.mozilla.org](https://addons.mozilla.org/firefox/addon/lockautopsy/)
- Machine payments (x402): the same deep report is sold per call at `https://lock-autopsy.smither.workers.dev/api/v1/x402/deep-audit` — $0.03 Base USDC, no account, no key. It is switched on in this deployment.

## Privacy and licence

No token addresses and no IP addresses are stored — see [PRIVACY.md](PRIVACY.md). MIT — see [LICENSE](LICENSE).

Contact: alex.ryder0201@gmail.com
