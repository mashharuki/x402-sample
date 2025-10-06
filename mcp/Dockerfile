# syntax=docker/dockerfile:1

FROM node:20-alpine

# Install pnpm
RUN corepack enable && corepack prepare pnpm@10.7.0 --activate

WORKDIR /app/mcp

# Copy all files
COPY mcp .

# Install dependencies
RUN pnpm install

# Run the MCP client
CMD ["npx", "tsx", "index.ts"]
