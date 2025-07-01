# MCP Random Name Server

A Model Context Protocol (MCP) server that provides a random name tool.

## Features

- **get_random_name**: Returns a random name from a predefined list of 5 names
- Built with TypeScript and the MCP SDK
- Containerized with Docker using node-alpine

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

### Docker
```bash
docker build -t mcp-random-name-server .
docker run mcp-random-name-server
```

## Available Tools

### get_random_name
Returns a random name from the predefined list: Alice, Bob, Charlie, Diana, Edward.

**Input:** None required

**Output:** A random name as text

## Development

- `npm run build` - Compile TypeScript
- `npm run watch` - Watch mode compilation
- `npm run dev` - Run with ts-node for development

## Requirements

- Node.js 18+
- TypeScript
- MCP SDK

## License

MIT