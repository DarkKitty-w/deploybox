# LockAutopsy

Is that token's locked supply actually locked? LockAutopsy reads vesting-contract
state directly from the chain and flags what websites don't tell you:
**cancelable streams, revocable vesting plans, exploited locker contracts, and
transferable lock NFTs** — the exact mechanisms behind "the dev rugged" stories.

## Free, unlimited, everywhere

- **Web inspector** — https://lock-autopsy.smither.workers.dev — paste any token address
- **Browser badge** — one click on DexScreener / GeckoTerminal / GMGN token pages:
  [Firefox (AMO)](https://addons.mozilla.org/firefox/addon/lockautopsy) ·
  [Chrome/Brave/Edge (Tampermonkey)](https://greasyfork.org/en/scripts/602782-lockautopsy-on-chain-token-vesting-lock-cancelability-auditor)
- **CLI** — `npx lock-autopsy <token-address> --chain base`
- **REST API** — `GET https://lock-autopsy.smither.workers.dev/api/v1/audit?address=…&chain=base`
- **AI agents (MCP)** — `io.github.DarkKitty-w/lock-autopsy` on the official
  MCP registry; add to Claude Desktop / Cursor with `npx lock-autopsy-mcp`
- **x402 machine payments** — `GET .../api/v1/x402/deep-audit?address=…` returns a
  $0.03 Base-USDC payment challenge; any agent that speaks x402 can pay-per-audit

## What a report looks like

```
Verdict : CRITICAL: CANCELABLE / REVOCABLE TOKEN LOCK DETECTED
  - Total Detected in Lockers     : 71.1%
  - Cancelable / Revocable / Risk : 71.1%
  * [71.1% supply] Sablier Lockup v3.0 (0xe261b3...)
    Flags  : SABLIER_IS_CANCELABLE_TRUE
    Verify : https://basescan.org/address/0xe261b3...#readContract
```

Every flag includes the on-chain call it came from and a block-explorer link —
**verify it yourself; never trust, verify.**

## Pro ($19 USDC, one-time, lifetime)

Free gives the verdict + breakdown. Pro adds per-stream IDs, exact unlock dates,
sender wallets, and the deployer's cross-token stream history (the "has this
wallet done this before?" answer). Keys at https://lock-autopsy.smither.workers.dev/pro
— pay on Base, key is `LA1...`, never expires, verified fully offline.

Protocols covered: Sablier (v1–v4, Curve/35-stream deep decode, Edge cases),
Hedgey (NFT + revocable plans + events), UNCX V2, Team Finance, PinkLock V2,
Solana Streamflow. Chains: Base, Ethereum, Arbitrum, BNB Chain, Solana.

_Read-only. No wallet connection. No financial advice — neutral on-chain state
only. MIT licensed._
