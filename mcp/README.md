# x402 MCP Example Client

This is an example client that demonstrates how to use the x402 payment protocol with the Model Context Protocol (MCP) to make paid API requests through an MCP server.

## Prerequisites

### For Local Development

- Node.js v20+ (install via [nvm](https://github.com/nvm-sh/nvm))
- pnpm v10 (install via [pnpm.io/installation](https://pnpm.io/installation))
- A running x402 server (you can use the example express server at `servers/express`)
- A valid Ethereum private key for making payments
- Claude Desktop with MCP support

### For Docker

- Docker and Docker Compose (install via [docs.docker.com/get-docker](https://docs.docker.com/get-docker/))
- A running x402 server (you can use the Docker-based express server)
- A valid Ethereum private key for making payments
- Claude Desktop with MCP support

## Setup

### Option 1: Local Development

1. Install and build all packages from the typescript examples root:

```bash
cd ../../
pnpm install
pnpm build
cd mcp
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
      "args": ["--silent", "-C", "<absolute path to this repo>/mcp", "dev"],
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

### Option 2: Docker

1. Copy `.env-local` to `.env` and add your Ethereum private key:

```bash
cp .env-local .env
```

2. Build the Docker image:

```bash
# From the repository root
docker build -f mcp/Dockerfile -t x402-mcp-client .
```

3. Run with Docker Compose (from repository root):

The MCP client is configured as a profile-based service, so it won't start automatically with other services.

```bash
# Start only the express server
docker-compose up -d express-server

# Start the MCP client (interactive mode)
docker-compose --profile mcp run --rm mcp-client
```

4. Configure Claude Desktop MCP settings for Docker:

```json
{
  "mcpServers": {
    "demo": {
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "--network=x402-sample_x402-network",
        "--env-file",
        "<absolute path to this repo>/mcp/.env",
        "x402-mcp-client"
      ]
    }
  }
}
```

**Note:** The MCP client uses stdio transport and requires interactive mode. When using with Claude Desktop, ensure the Docker network allows communication with the express server.
