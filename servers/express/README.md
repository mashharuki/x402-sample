# x402-express Example Server

This is an example Express.js server that demonstrates how to use the `x402-express` middleware to implement paywall functionality in your API endpoints.

## Prerequisites

### For Local Development

- Node.js v20+ (install via [nvm](https://github.com/nvm-sh/nvm))
- pnpm v10 (install via [pnpm.io/installation](https://pnpm.io/installation))
- A valid Ethereum address for receiving payments
- Coinbase Developer Platform API Key & Secret (if accepting payments on Base mainnet) -- Get them here [https://portal.cdp.coinbase.com/projects](https://portal.cdp.coinbase.com/projects)

### For Docker

- Docker and Docker Compose (install via [docs.docker.com/get-docker](https://docs.docker.com/get-docker/))
- A valid Ethereum address for receiving payments
- Coinbase Developer Platform API Key & Secret (if accepting payments on Base mainnet)

## Setup

### Option 1: Local Development

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

### Option 2: Docker

1. Copy `.env-local` to `.env` and add your Ethereum address to receive payments:

```bash
cp .env-local .env
```

2. Build and run with Docker Compose:

```bash
docker-compose up -d
```

3. View logs:

```bash
docker-compose logs -f
```

4. Stop the server:

```bash
docker-compose down
```

## Accessing the Server

Once running (either locally or via Docker), the server will be available at:

- http://localhost:4021/weather
