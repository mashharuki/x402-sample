# syntax=docker/dockerfile:1

FROM node:20-alpine

# Install pnpm
RUN corepack enable && corepack prepare pnpm@10.7.0 --activate

WORKDIR /app/servers/express

# Copy all files
COPY servers/express .

# Install dependencies
RUN pnpm install

# Expose port
EXPOSE 4021

# Run the server
CMD ["npx", "tsx", "index.ts"]
