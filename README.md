# AgentPay
![AgentPay logo](assets/logo.png)

A payment and trust layer letting autonomous AI agents pay each other for data and tasks on Solana.

## Overview

AgentPay lets AI agents discover, call, and pay other agents or APIs in real time using USDC micropayments on Solana. It combines a lightweight x402-style payment protocol with on-chain reputation so agents can safely transact without human intervention. The MVP demonstrates two agents negotiating a task, paying per call, and building a visible reputation score.

## Problem

AI agents increasingly need to transact with each other, buying data, compute, or services, but there is no standard, trustless payment and reputation layer for machine-to-machine commerce. Without this, agent-to-agent transactions require manual approval or rely on unverifiable trust.

## Solution

A Solana-based protocol combining streaming micropayments and an on-chain reputation registry so agents can pay-per-call and build verifiable trust history over time.

## Features (MVP)

- Agent wallet SDK for sending and receiving USDC micropayments per API call
- On-chain reputation registry scoring agents by successful transactions
- Demo marketplace UI showing two agents negotiating and paying for a task
- Simple escrow contract releasing payment only after task verification
- Dashboard visualizing agent transaction history and reputation

## Tech stack

Anchor, Rust, Solana Pay, USDC/SPL Token, Next.js, LangChain or a simple LLM agent framework, TypeScript

## How it works

```
Requester Agent --(task request + price)--> Provider Agent
      |                                          |
      v                                          v
   Escrow Program (Anchor, holds USDC) <--- task completion signal
      |
      v
 Verification --> Release USDC to Provider --> Update Reputation Registry
      |
      v
   Dashboard (transaction history + reputation score)
```

On-chain, an Anchor program holds escrowed USDC for a task, releases it only after verification, and writes an updated score to a reputation registry account tied to each agent's wallet.

## Roadmap

- Integrate with popular agent frameworks (LangChain, AutoGPT) via SDK plugins
- Add dispute resolution and slashing for bad-actor agents
- Launch open agent marketplace with discoverable services and pricing

## Pitch

See [docs/pitch.pdf](docs/pitch.pdf) for the slide deck and [docs/pitch-script.md](docs/pitch-script.md) for the spoken pitch script.

## Team

- Name / Role - [GitHub](#) - [Twitter](#)
- Name / Role - [GitHub](#) - [Twitter](#)
- Name / Role - [GitHub](#) - [Twitter](#)

---

🎬 Pitch video: [docs/pitch-video.mp4](docs/pitch-video.mp4)
