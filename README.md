# Swapper AI Agent Toolkit

The payment layer for AI agents. Deposit funds, swap tokens, and manage wallets — directly from your AI agent or coding assistant.

Works with [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Cursor](https://cursor.com), [Windsurf](https://windsurf.com), [OpenClaw](https://openclaw.com), [GitHub Copilot](https://copilot.github.com), [CrewAI](https://crewai.com), [AutoGPT](https://autogpt.net), and any AI agent framework that supports the open skills standard.

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

## FAQ

### General

**What is Swapper AI Agent Toolkit?**
Swapper is a payment layer for AI agents that enables deposit, swap, and wallet management capabilities directly from coding assistants and AI agent frameworks. It works with Claude Code, Cursor, Windsurf, GitHub Copilot, CrewAI, and any agent supporting the open skills standard.

**Which blockchains are supported?**
Swapper supports 60+ blockchains via Chainlink CCIP cross-chain infrastructure, including Ethereum, Arbitrum, Base, Optimism, Polygon, and more.

### Installation & Setup

**How do I install the toolkit?**
Run `npx skills add swapperfinance/swapper-toolkit` in your project directory. The skills will be available to your AI agent or coding assistant.

**Do I need a Swapper account?**
No. Swapper works with any wallet address. Transactions require explicit user confirmation for security.

### Wallet & Deposits

**How does wallet management work?**
The `/swapper-wallet` skill enables smart wallet creation with account abstraction, multi-chain setup, and funding via fiat or crypto. Private keys are never stored or accessed by Swapper.

**What deposit methods are available?**
Direct crypto transfers, cross-chain bridge transfers via Chainlink CCIP, protocol deposits (lending, staking, liquidity pools), and fiat on-ramp through Mastercard, Visa, Apple Pay, and Google Pay across 170+ countries.

### Safety & Security

**Are transactions auto-approved?**
No. Every transaction requires explicit user confirmation. Slippage, gas fees, and risks are surfaced before confirmation. Private keys are never stored or accessed.

### Troubleshooting

**Deposit not appearing in wallet**
Check the transaction hash on the block explorer. Cross-chain transfers via Chainlink CCIP may take several minutes. Verify the destination chain and token address are correct.

**Skill not recognized by AI agent**
Ensure the skill was installed correctly with `npx skills add`. Restart your coding assistant after installation. Check that your agent supports the open skills standard.

**Fiat deposit failing**
Verify your card is supported (Mastercard, Visa, Apple Pay, or Google Pay). Ensure your country is within the 170+ supported regions. Contact Swapper support if the issue persists.

---


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