# DAO Governance Alpha

A robust and secure smart contract suite for Decentralized Autonomous Organizations (DAOs). This repository provides the core logic for community-led decision-making, allowing token holders to propose and vote on on-chain actions.

## Overview
The system utilizes an ERC-20 token with "snapshots" or delegation to track voting power fairly. Proposals are submitted as a series of target addresses and data payloads, which are automatically executed by the DAO treasury upon reaching a successful quorum and majority vote.

### Key Features
* **Token-Weighted Voting:** Integration with ERC20Votes for gas-efficient snapshots.
* **Proposal Lifecycle:** Managed stages including Pending, Active, Defeated, Succeeded, and Executed.
* **Configurable Governance:** Easily adjust voting delay, voting period, and quorum percentage.
* **Timelock Ready:** Designed to be used with a Timelock controller to prevent "flash-governance" attacks.

## Technical Stack
* **Language:** Solidity ^0.8.20
* **Standards:** OpenZeppelin Governor, ERC-20
* **License:** MIT

## Workflow
1. Users delegate their voting power (even to themselves).
2. A proposer submits a proposal via `propose()`.
3. After the `votingDelay`, the proposal becomes `Active`.
4. Token holders cast votes (For, Against, or Abstain).
5. If the proposal passes, it is queued and then executed.
