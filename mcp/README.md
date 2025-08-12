# x402 MCP Example Client

This is an example client that demonstrates how to use the x402 payment protocol with the Model Context Protocol (MCP) to make paid API requests through an MCP server.

## Prerequisites

- Node.js v20+ (install via [nvm](https://github.com/nvm-sh/nvm))
- pnpm v10 (install via [pnpm.io/installation](https://pnpm.io/installation))
- A running x402 server (you can use the example express server at `examples/typescript/servers/express`)
- A valid Ethereum private key for making payments
- Claude Desktop with MCP support

## Setup

1. Install and build all packages from the typescript examples root:

```bash
cd ../../
pnpm install
pnpm build
cd clients/mcp
```

2. Copy `.env-local` to `.env` and add your Ethereum private key:

```bash
cp .env-local .env
```

3. Configure Claude Desktop MCP settings:

```json
{
  "mcpServers": {
    "demo": {
      "command": "pnpm",
      "args": [
        "--silent",
        "-C",
        "<absolute path to this repo>/examples/typescript/clients/mcp",
        "dev"
      ],
      "env": {
        "PRIVATE_KEY": "<private key of a wallet with USDC on Base Sepolia>",
        "RESOURCE_SERVER_URL": "http://localhost:4021",
        "ENDPOINT_PATH": "/weather"
      }
    }
  }
}
```

4. Start the example client (remember to be running a server or pointing to one in the .env file):

```bash
pnpm dev
```
