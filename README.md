# MCP Random Name Server

A Model Context Protocol (MCP) server that provides a random name tool using **Streamable HTTP transport**.

## Features

- **get_random_name**: Returns a random name from a predefined list of 5 names
- Built with TypeScript and the MCP SDK (v1.13.2)
- Uses modern Streamable HTTP transport (not legacy stdio)
- Containerized with Docker using node-alpine
- Express.js HTTP server with session management

## Installation

```bash
npm install
npm run build
```

## Usage

### Local Development
```bash
npm run dev
```

### Production
```bash
npm start
```

The server will start on port 3000 by default (configurable via `PORT` environment variable).

### Docker
```bash
docker build -t mcp-random-name-server .
docker run -p 3000:3000 mcp-random-name-server
```

## API Endpoints

- `POST /mcp` - Main MCP endpoint for client communication
- `GET /mcp` - Server-sent events for notifications (with session ID)
- `DELETE /mcp` - Session termination (with session ID)
- `GET /health` - Health check endpoint
- `GET /` - Server information

## Available Tools

### get_random_name
Returns a random name from the predefined list: Alice, Bob, Charlie, Diana, Edward.

**Input:** None required

**Output:** A random name as text

## MCP Transport

This server uses the **Streamable HTTP transport** which supports:
- Session management with UUIDs
- Server-sent events for real-time notifications
- HTTP POST for client-to-server communication
- Proper MCP protocol compliance

### Client Connection

Clients should connect to the `/mcp` endpoint using the Streamable HTTP transport protocol. The server handles session initialization, maintains state, and supports both request/response and streaming scenarios.

## Development

- `npm run build` - Compile TypeScript
- `npm run watch` - Watch mode compilation
- `npm run dev` - Run with ts-node for development

## Requirements

- Node.js 18+
- TypeScript
- MCP SDK 1.13.2
- Express.js

## Environment Variables

- `PORT` - Server port (default: 3000)
- `NODE_ENV` - Environment mode

## License

MIT