# x402-express Example Server

This is an example Express.js server that demonstrates how to use the `x402-express` middleware to implement paywall functionality in your API endpoints.

## Prerequisites

- Node.js v20+ (install via [nvm](https://github.com/nvm-sh/nvm))
- pnpm v10 (install via [pnpm.io/installation](https://pnpm.io/installation))
- A valid Ethereum address for receiving payments
- Coinbase Developer Platform API Key & Secret (if accepting payments on Base mainnet) -- Get them here [https://portal.cdp.coinbase.com/projects](https://portal.cdp.coinbase.com/projects)

## Setup

1. Copy `.env-local` to `.env` and add your Ethereum address to receive payments:

```bash
cp .env-local .env
```

2. Install and build all packages from the typescript examples root:

```bash
cd ../../
pnpm install
pnpm build
cd servers/express
```

3. Run the server

```bash
pnpm install
pnpm dev
```
