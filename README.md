# LockAutopsy

LockAutopsy helps you inspect token vesting and lock contracts for conditions such as cancellation, revocation, and transferable lock NFTs. It reads on-chain data without asking you to connect a wallet.

**[Open the web inspector](https://lock-autopsy.smither.workers.dev/)**

## What it checks

LockAutopsy supports selected lock and vesting contracts on Base, Ethereum, Arbitrum, BNB Chain, and Solana. Supported protocols include Sablier, Hedgey, UNCX, Team Finance, PinkLock, and Streamflow.

A report can show whether a detected lock is cancelable, revocable, or transferable, along with links to help you inspect the relevant contracts.

**Important:** Coverage is limited to the contracts and data sources the tool supports. A clean or empty result does not prove that a token is safe, and an unavailable data source can make a report incomplete. Verify important findings independently. This tool is not financial advice.

## Use it on the web

1. Open the [web inspector](https://lock-autopsy.smither.workers.dev/).
2. Paste a token contract address or Solana mint address.
3. Select the chain and run the check.

The basic report is free. No account or wallet connection is required to run it.

## Use the command line

Requires Node.js 20 or newer. Start with:

```bash
npx --yes lock-autopsy --help
```

To check a token, replace `TOKEN_ADDRESS` with its contract address:

```bash
npx --yes lock-autopsy TOKEN_ADDRESS --chain base
```

The supported chain values are `base`, `ethereum`, `arbitrum`, `bsc`, and `solana`. Add `--json` for JSON output.

## Use with an MCP client

The server is listed in the [official MCP registry](https://registry.modelcontextprotocol.io/v0.1/servers/io.github.DarkKitty-w%2Flock-autopsy/versions/latest) as `io.github.DarkKitty-w/lock-autopsy`.

For a client that launches an MCP server over standard input and output, use `npx` with these arguments:

```json
{
  "mcpServers": {
    "lock-autopsy": {
      "command": "npx",
      "args": ["--yes", "--package=lock-autopsy", "lock-autopsy-mcp"]
    }
  }
}
```

The configuration file and setup steps depend on your MCP client.

## Browser userscript

A [GreasyFork userscript](https://greasyfork.org/en/scripts/602782-lockautopsy-on-chain-token-vesting-lock-cancelability-auditor) is available for supported token pages. **Current setup note:** its default server address is incorrect. In the script's **Key/API** settings, set **Worker Origin** to `https://lock-autopsy.smither.workers.dev` before using it. If the server is unavailable, the script warns that its fallback check is partial. Do not treat a partial or empty result as a safety verdict.

## Pro

[LockAutopsy Pro](https://lock-autopsy.smither.workers.dev/pro) is a one-time purchase starting at **19 USDC on Base**. Each invoice includes a small unique decimal amount—less than 0.01 USDC above 19—so send the **exact amount shown** on your invoice. Network fees are separate.

Pro provides additional detail, such as per-stream information and sender-related data where available. Usage limits apply to the hosted service. Save your claim secret securely: it is needed with your transaction hash to claim or recover your key. Never share your claim secret or Pro key.

## API

The public audit endpoint accepts a token address and chain:

```text
GET https://lock-autopsy.smither.workers.dev/api/v1/audit?address=TOKEN_ADDRESS&chain=base
```

Replace `TOKEN_ADDRESS` with the address to check. An x402 endpoint is also available for paid agent requests at `/api/v1/x402/deep-audit`; the displayed price is 0.03 USDC on Base per request.

## Feedback

Questions about the userscript can be posted on its [GreasyFork feedback page](https://greasyfork.org/en/scripts/602782-lockautopsy-on-chain-token-vesting-lock-cancelability-auditor/feedback).

The npm package declares the MIT license.
