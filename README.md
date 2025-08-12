# X402 Examples

This directory contains a collection of TypeScript examples demonstrating how to use the X402 protocol in various contexts. These examples are designed to work with the X402 npm packages and share a workspace with the main X402 packages.

## Setup

Before running any examples, you need to install dependencies and build the packages:

```bash
pnpm install
pnpm build
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
