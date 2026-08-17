<p align="center">
  <img src="public/ethvault-logo.svg" width="100" alt="ETHVault logo" />
</p>

<h1 align="center">ETHVault</h1>
<p align="center"><b>An Ethereum staking and governance platform: deposit ETH, stake it, earn rewards, and vote on proposals.</b></p>

<p align="center">
  <img alt="Next.js" src="https://img.shields.io/badge/frontend-Next.js-000000?logo=nextdotjs&logoColor=white">
  <img alt="Solidity" src="https://img.shields.io/badge/contracts-Solidity-363636?logo=solidity&logoColor=white">
  <img alt="ethers.js" src="https://img.shields.io/badge/chain-ethers.js-2535A0?logo=ethereum&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/typescript-3178C6?logo=typescript&logoColor=white">
</p>

ETHVault models a two-step staking flow on top of four Solidity
contracts: deposit ETH to receive an ERC-20 receipt token, stake that
token to receive a second ERC-20 representing your staked position, earn
rewards, and vote on governance proposals with a dashboard tracking
protocol-wide stats and a staking leaderboard.

## Smart contracts

| Contract | Role |
|---|---|
| `dETH.sol` | ERC-20 minted 1:1 when a user deposits ETH |
| `sETH.sol` | ERC-20 minted when a user stakes their dETH |
| `Governance.sol` | proposal creation, voting, execution |
| `StakingDashboard.sol` | on-chain stats and leaderboard data |

## Stack

- **Frontend**: Next.js (App Router), React, TypeScript, Tailwind CSS,
  shadcn/ui.
- **Chain**: ethers.js against contracts deployed on the Ethereum
  Holesky testnet.
- **State**: React hooks, no external state library.

## Running it locally

Requirements: Node.js 20.12.2+, MetaMask (or another wallet), and access
to the Holesky testnet.

```bash
git clone https://github.com/Heet852003/ethvault.git
cd ethvault
npm install
npm run dev
```

Open http://localhost:3000, connect a wallet on Holesky, and you can
deposit, stake, and vote.

## Repository layout

```
app/              Next.js pages: deposit, stake, governance, leaderboard
components/        layout and UI components (shadcn/ui-based)
contracts/         the four Solidity contracts
hooks/             custom React hooks for contract interaction
lib/abis/          contract ABIs consumed by the frontend
```