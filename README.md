# Swapper AI Agent Toolkit

The payment layer for AI agents. Deposit funds, swap tokens, and manage wallets — directly from your AI agent or coding assistant.

Works with [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Cursor](https://cursor.com), [Windsurf](https://windsurf.com), [OpenClaw](https://openclaw.com), [Autohand Code CLI](https://github.com/autohandai/code-cli), [GitHub Copilot](https://copilot.github.com), [CrewAI](https://crewai.com), [AutoGPT](https://autogpt.net), and any AI agent framework that supports the open skills standard.

Powered by [Chainlink CRE](https://chain.link/cre), [Chainlink CCIP](https://chain.link/cross-chain), and [Mastercard](https://mastercard.com).

## Installation

```bash
npx skills add swapperfinance/swapper-toolkit
```

## Available Skills

### `/swapper-deposit` — Direct Deposit

Deposit and bridge funds into wallets and DeFi protocols. Card, wallet, or crypto transfer — straight into the protocol.

- Direct deposits to any wallet address
- Cross-chain bridge transfers via Chainlink CCIP
- Protocol deposits — lending, staking, liquidity pools
- Fiat on-ramp — Mastercard, Visa, Apple Pay, Google Pay (170+ countries)

**Triggers when:**
- User asks to deposit, fund, top-up, or bridge assets
- Agent detects a wallet has insufficient funds mid-task
- User wants to convert fiat to crypto and deposit into DeFi
- User wants to fund a wallet before executing a strategy

**Example:**

```
User: "Deposit $100 USDC into Aave on Base"

Swapper Deposit Skill:
→ Chain: Base (8453)
→ Token: USDC
→ Protocol: Aave
→ Amount: $100
→ Opening deposit link...

✓ Deposit link generated. Confirm in your browser.
```

**Supported chains:** Ethereum, Base, Arbitrum, Optimism, Polygon, Fast, Solana, HyperEVM, BNB Chain, Avalanche

### `/swapper-trade` — Token Swap *(Coming Soon)*

Swap tokens across chains and DEXs. Cross-chain swaps via Chainlink CCIP.

- Same-chain swaps across major DEXs
- Cross-chain swaps via CCIP
- Optimal route finding
- Slippage protection

### `/swapper-wallet` — Wallet Management *(Coming Soon)*

Create, fund, and manage agent wallets.

- Smart wallet creation with account abstraction
- Multi-chain wallet setup
- Wallet funding via fiat or crypto
- Balance checking

## SDK Integration

For developers building apps who want to embed the deposit flow:

```bash
npm i @swapper-finance/deposit-sdk
```

```javascript
import { openSwapperModal } from "@swapper-finance/deposit-sdk";

openSwapperModal({
  integratorId: "your-integrator-id",
  dstChainId: "8453",
  dstTokenAddr: "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913",
  depositWalletAddress: "0xYourWalletAddress",
  styles: { themeMode: "dark" },
  supportedDepositOptions: ["transferCrypto", "depositWithCash"],
});
```

## Safety

- **Explicit confirmation** — every transaction requires user approval
- **Transparent fees** — slippage, gas, and risks surfaced before confirmation
- **Key security** — private keys are never stored or accessed
- Transactions are never auto-approved

## Powered by

- **[Chainlink CRE](https://chain.link/cre)** — End-to-end workflow orchestration for deposits, compliance, and settlement
- **[Chainlink CCIP](https://chain.link/cross-chain)** — Cross-chain interoperability across 60+ blockchains
- **[Mastercard](https://mastercard.com)** — Global card payment processing (170+ countries)

## Documentation

- [Full docs](https://docs.swapper.finance/ai-agents/skills)
- [Swapper Finance](https://swapper.finance)

## License

[MIT](LICENSE)
