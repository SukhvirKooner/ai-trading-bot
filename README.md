# AI Crypto Trading Agent

An autonomous multi-model AI trading agent that uses LLMs (Claude, DeepSeek, Qwen) to analyze real-time cryptocurrency market data and execute leveraged trades on the Lighter DEX protocol.

## Tech Stack

- **Runtime:** Node.js / TypeScript
- **AI:** Vercel AI SDK, OpenRouter (multi-model)
- **Backend:** Express.js, PostgreSQL, Prisma ORM
- **Frontend:** React 19, Recharts, Tailwind CSS
- **Trading:** Lighter DEX SDK

## Features

- Multi-model AI agents running in parallel with independent portfolios
- Real-time data pipeline with EMA-20 and MACD technical indicators
- Automated 5-minute trading cycles with leveraged positions (up to 10x)
- Full-stack monitoring dashboard with portfolio performance charts
- Persistent logging of all agent decisions and trade metadata

## Setup

### Prerequisites

- Node.js 18+
- PostgreSQL database
- OpenRouter API key
- Lighter DEX API key

### Installation

```bash
npm install
```

### Environment Variables

Copy `.env.example` to `.env` and fill in your keys:

```bash
cp .env.example .env
```

### Database Setup

```bash
npx prisma migrate dev
npx prisma generate
```

### Run the Agent

```bash
npx ts-node index.ts
```

### Run the Dashboard

```bash
cd frontend
npm install
npm run dev
```

## Architecture

```
Agent Loop (5 min) → Fetch Market Data → Compute Indicators → LLM Decision → Execute Trade
                                                                                    ↓
Price Tracker (2 min) → Snapshot Portfolio → PostgreSQL ← Express API ← React Dashboard
```
