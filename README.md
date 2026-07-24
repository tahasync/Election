# Election Voting DApp

A Truffle-based Ethereum DApp with a Solidity smart contract that implements a two-candidate voting system (Imran Khan, Nawaz Sharif) — one-person-one-vote enforced on-chain, with a Pakistan-themed HTML/JS frontend connected via MetaMask.

## What it does

Deploys a Solidity contract to a local Ganache chain that stores candidates and votes in mappings, prevents double-voting per address, and emits events on each vote. A frontend connects via Web3.js, loads the contract artifact, renders candidate names and vote counts, and allows wallet-connected users to cast their single vote. Three Mocha/Chai tests verify initialization, candidate values, and vote casting with double-vote rejection.

**Candidates are hardcoded** — the contract constructor registers "Imran Khan" and "Nawaz Sharif" at deployment time. Requires Ganache (local testnet only — no testnet/mainnet config).

## Tech stack

- Solidity 0.4.25, Truffle, Web3.js 0.20.6 (deprecated), Ganache
- Frontend: HTML, CSS, JavaScript (Bootstrap 3, jQuery 1.12 via CDN)
- Testing: Mocha + Chai (3 tests)

## Setup

```bash
npm install -g truffle
npm install
# Start Ganache on localhost:8545
truffle compile
truffle migrate --reset --network development
# Open src/index.html in browser with MetaMask on localhost:8545
```

## Status

**Academic project — complete.** Works on Ganache local net. The Solidity version (0.4.25) and Web3.js (0.20.x) are outdated but functional. The two candidates are hardcoded in the contract constructor, so redeployment with code changes is needed for different elections.