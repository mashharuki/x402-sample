# X402 Examples

This directory contains a collection of TypeScript examples demonstrating how to use the X402 protocol in various contexts. These examples are designed to work with the X402 npm packages and share a workspace with the main X402 packages.

## Setup

### Option 1: Local Development

Before running any examples, you need to install dependencies and build the packages:

```bash
pnpm install
pnpm build
```

### Option 2: Docker

You can run the examples using Docker and Docker Compose:

1. Ensure Docker and Docker Compose are installed on your system
2. Copy `.env-local` to `.env` in each service directory and configure your environment variables
3. Build and run with Docker Compose:

```bash
# Start all services (currently only express-server starts by default)
docker-compose up -d

# View logs
docker-compose logs -f

# Stop all services
docker-compose down
```

For the MCP client (which requires interactive mode):

```bash
# Start the express server first
docker-compose up -d express-server
```

## Example Structure

The examples are organized into several categories:

### Clients

- `mcp/` - Example using MCP (Model Context Protocol) as a client using `x402-axios`

### Servers

- `express/` - Example using Express.js with `x402-express`

## Running Examples

Each example directory contains its own README with specific instructions for running that example. Navigate to the desired example directory and follow its instructions.

## Development

This workspace uses:

- pnpm for package management
- Turborepo for monorepo management
- TypeScript for type safety

The examples are designed to work with the main X402 packages, so they must be built before running any examples.

## A note on private keys

The examples in this folder commonly use private keys to sign messages. **Never put a private key with mainnet funds in a `.env` file**. This can result in keys getting checked into codebases and being drained.
