<div align="center" style="margin: 0 auto; max-width: 80%;">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/mcp-use/mcp-use-ts/main/packages/mcp-use/static/logo_white.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/mcp-use/mcp-use-ts/main/packages/mcp-use/static/logo_black.svg">
    <img alt="mcp use logo" src="https://raw.githubusercontent.com/mcp-use/mcp-use-ts/main/packages/mcp-use/static/logo_white.svg" width="80%" style="margin: 20px auto;">
  </picture>
</div>

<h1 align="center">MCP Inspector</h1>

<p align="center">
    <a href="https://www.npmjs.com/package/@mcp-use/inspector" alt="NPM Downloads">
        <img src="https://img.shields.io/npm/dw/@mcp-use/inspector.svg"/></a>
    <a href="https://www.npmjs.com/package/@mcp-use/inspector" alt="NPM Version">
        <img src="https://img.shields.io/npm/v/@mcp-use/inspector.svg"/></a>
    <a href="https://github.com/mcp-use/mcp-use/blob/main/LICENSE" alt="License">
        <img src="https://img.shields.io/github/license/mcp-use/mcp-use-ts" /></a>
    <a href="https://github.com/mcp-use/mcp-use/stargazers" alt="GitHub stars">
        <img src="https://img.shields.io/github/stars/mcp-use/mcp-use-ts?style=social" /></a>
    <a href="https://discord.gg/XkNkSkMz3V" alt="Discord">
        <img src="https://dcbadge.limes.pink/api/server/XkNkSkMz3V?style=flat" /></a>
</p>

🔍 **MCP Inspector by mcp-use** is an open-source, interactive developer tool for testing and debugging MCP servers with support for MCP-UI and OpenAI Apps SDK widgets. It provides a beautiful, intuitive interface for testing tools, exploring resources, managing prompts, and monitoring server connections - all from your browser.

## 🚀 Try it:

- **Online**: [inspector.mcp-use.com](https://inspector.mcp-use.com/inspector)
- **Locally**: Run `npx @mcp-use/inspector`
- **Repository**: [github.com/mcp-use/mcp-use](https://github.com/mcp-use/mcp-use/tree/main/libraries/typescript/packages/inspector)

## 🎥 Demo

[![mcp-use inspector demo video](https://github.com/user-attachments/assets/4ef1643b-6f28-473e-8e7b-40c0c454d69d)](https://www.youtube.com/watch?v=DvsNSABz1GM)


### 📖 Documentation

For detailed usage instructions and guides, visit [docs.mcp-use.com/inspector](https://docs.mcp-use.com/inspector)

---

## 📦 Related Packages

| Package                                                                                           | Description             | Version                                                                                                         |
| ------------------------------------------------------------------------------------------------- | ----------------------- | --------------------------------------------------------------------------------------------------------------- |
| [mcp-use](https://github.com/mcp-use/mcp-use-ts/tree/main/packages/mcp-use)                       | Core MCP framework      | [![npm](https://img.shields.io/npm/v/mcp-use.svg)](https://www.npmjs.com/package/mcp-use)                       |
| [@mcp-use/cli](https://github.com/mcp-use/mcp-use-ts/tree/main/packages/cli)                      | Build tool for MCP apps | [![npm](https://img.shields.io/npm/v/@mcp-use/cli.svg)](https://www.npmjs.com/package/@mcp-use/cli)             |
| [create-mcp-use-app](https://github.com/mcp-use/mcp-use-ts/tree/main/packages/create-mcp-use-app) | Create MCP apps         | [![npm](https://img.shields.io/npm/v/create-mcp-use-app.svg)](https://www.npmjs.com/package/create-mcp-use-app) |
| Package                                                                                           | Description             | Version                                                                                                         |
| ------------------------------------------------------------------------------------------------- | ----------------------- | --------------------------------------------------------------------------------------------------------------- |
| [mcp-use](https://github.com/mcp-use/mcp-use-ts/tree/main/packages/mcp-use)                       | Core MCP framework      | [![npm](https://img.shields.io/npm/v/mcp-use.svg)](https://www.npmjs.com/package/mcp-use)                       |
| [@mcp-use/cli](https://github.com/mcp-use/mcp-use-ts/tree/main/packages/cli)                      | Build tool for MCP apps | [![npm](https://img.shields.io/npm/v/@mcp-use/cli.svg)](https://www.npmjs.com/package/@mcp-use/cli)             |
| [create-mcp-use-app](https://github.com/mcp-use/mcp-use-ts/tree/main/packages/create-mcp-use-app) | Create MCP apps         | [![npm](https://img.shields.io/npm/v/create-mcp-use-app.svg)](https://www.npmjs.com/package/create-mcp-use-app) |

---

## ✨ Key Features

| Feature                    | Description                                                     |
| -------------------------- | --------------------------------------------------------------- |
| **🚀 Auto-Mount**          | Automatically available at `/inspector` for all MCP-Use servers |
| **🔌 Multi-Connection**    | Connect to and manage multiple MCP servers simultaneously       |
| **🎯 Interactive Testing** | Test tools with live execution and real-time results            |
| **📊 Real-time Status**    | Monitor connection states, errors, and server health            |
| **🔐 OAuth Support**       | Built-in OAuth flow handling with popup authentication          |
| **💾 Persistent Sessions** | Connections saved to localStorage and auto-reconnect            |
| **🎨 Beautiful UI**        | Modern, responsive interface built with React and Tailwind      |
| **🔍 Tool Explorer**       | Browse and execute all available tools with schema validation   |
| **📁 Resource Browser**    | View and copy resource URIs with syntax highlighting            |
| **💬 Prompt Manager**      | Test and manage prompts with argument templates                 |
| **🌐 Universal Support**   | Works with HTTP/SSE and WebSocket connections                   |

---

## 🚀 Quick Start

### Method 1: Automatic with mcp-use Server (Recommended)

When you create an MCP server with `mcp-use`, the inspector is automatically available at `/inspector`:

```typescript
import { createMCPServer } from 'mcp-use/server'

const server = createMCPServer('my-server', {
  version: '1.0.0',
})

// Add your tools, resources, prompts...

server.listen(3000)
// 🎉 Inspector automatically available at http://localhost:3000/inspector
// 🚀 Auto-connects to your local server at http://localhost:3000/mcp
```

**That's it!** No additional configuration needed. The inspector:

- Automatically mounts at `/inspector`
- Auto-connects to your local MCP server
- Provides instant debugging capabilities
- Opens automatically in dev mode with `@mcp-use/cli`

### Method 2: Standalone CLI Tool

Use the inspector with any MCP server (local or remote):

```bash
# Inspect a remote server
npx @mcp-use/inspector --url https://mcp.linear.app/sse

# Custom port
npx @mcp-use/inspector --url http://localhost:3000/mcp --port 8080

# Open inspector without auto-connect
npx @mcp-use/inspector
```

### Method 3: Custom Integration

Mount the inspector in your Express app at a custom path:

```typescript
import { mountInspector } from '@mcp-use/inspector'
import express from 'express'

const app = express()

// Mount at custom path
mountInspector(app, '/debug/inspector')

app.listen(3000)
// Inspector available at http://localhost:3000/debug/inspector
// 🚀 Auto-connects to your local server at http://localhost:3000/mcp
```

**That's it!** No additional configuration needed. The inspector:

- Automatically mounts at `/inspector`
- Auto-connects to your local MCP server
- Provides instant debugging capabilities
- Opens automatically in dev mode with `@mcp-use/cli`

### Method 2: Standalone CLI Tool

Use the inspector with any MCP server (local or remote):

```bash
# Inspect a remote server
npx @mcp-use/inspector --url https://mcp.linear.app/sse

# Custom port
npx @mcp-use/inspector --url http://localhost:3000/mcp --port 8080

# Open inspector without auto-connect
npx @mcp-use/inspector
```

### Method 3: Custom Integration

Mount the inspector in your Express app at a custom path:

```typescript
import { mountInspector } from '@mcp-use/inspector'
import express from 'express'

const app = express()

// Mount at custom path
mountInspector(app, '/debug/inspector')

app.listen(3000)
// Inspector available at http://localhost:3000/debug/inspector
```

---

## 📖 Usage Guide

### Dashboard Overview

The main dashboard shows:

- **Connected Servers Panel** (left): View all your connected servers
- **Connect Panel** (right): Add new server connections with transport, URL, auth, and headers configuration
- **Quick Actions**: Access settings and clear sessions from the top bar

### Adding an MCP Server

To connect to an MCP server:

1. **Open Connect Panel**: Click the Connect panel on the right side of the dashboard
2. **Configure Transport**:
   - Select "Streamable HTTP" for SSE connections
   - Select "WebSocket" for WS connections
   - Configure "stdin/stdio" for local process connections
3. **Enter Server URL**: Input the MCP server endpoint (e.g., `https://mcp.linear.app/mcp`)
4. **Configure Authentication** (if needed): Add OAuth credentials or API headers
5. **Click Connect**: Establish the connection

Example URLs:


- Local: `http://localhost:3000/mcp`
- Linear: `https://mcp.linear.app/sse`
- WebSocket: `ws://localhost:8080`

### Connection States

The inspector displays real-time connection states:

| State                 | Description                | Action             |
| --------------------- | -------------------------- | ------------------ |
| 🔍 **discovering**    | Finding the server         | Wait               |
| 🔄 **connecting**     | Establishing connection    | Wait               |
| 🔐 **authenticating** | OAuth flow in progress     | Complete auth      |
| 📥 **loading**        | Loading tools & resources  | Wait               |
| ✅ **ready**          | Connected and operational  | Use tools          |
| ❌ **failed**         | Connection failed          | Retry              |
| ⏳ **pending_auth**   | Waiting for authentication | Click Authenticate |

### Testing Tools

1. Click **"Inspect"** on a connected server
2. Navigate to the **Tools** tab
3. Select a tool to view its schema
4. Click **"Execute"** to open the test panel
5. Enter JSON parameters
6. Click **"Run"** to execute
7. View results in real-time

Example tool execution:

```json
// Input for 'search_database' tool
{
  "query": "user analytics",
  "limit": 10,
  "sortBy": "date"
}

// Result
{
  "results": [...],
  "total": 42,
  "executionTime": "23ms"
}
```
- Linear: `https://mcp.linear.app/sse`
- WebSocket: `ws://localhost:8080`

### Connection States

The inspector displays real-time connection states:

| State                 | Description                | Action             |
| --------------------- | -------------------------- | ------------------ |
| 🔍 **discovering**    | Finding the server         | Wait               |
| 🔄 **connecting**     | Establishing connection    | Wait               |
| 🔐 **authenticating** | OAuth flow in progress     | Complete auth      |
| 📥 **loading**        | Loading tools & resources  | Wait               |
| ✅ **ready**          | Connected and operational  | Use tools          |
| ❌ **failed**         | Connection failed          | Retry              |
| ⏳ **pending_auth**   | Waiting for authentication | Click Authenticate |

### Testing Tools

1. Click **"Inspect"** on a connected server
2. Navigate to the **Tools** tab
3. Select a tool to view its schema
4. Click **"Execute"** to open the test panel
5. Enter JSON parameters
6. Click **"Run"** to execute
7. View results in real-time

Example tool execution:

```json
// Input for 'search_database' tool
{
  "query": "user analytics",
  "limit": 10,
  "sortBy": "date"
}

// Result
{
  "results": [...],
  "total": 42,
  "executionTime": "23ms"
}
```

### OAuth Authentication

For servers requiring OAuth (like Linear):

1. After clicking **Connect**, you'll see the authorization page
2. Click **"Approve"** to grant access
3. The inspector handles the redirect automatically
4. Server appears in Connected Servers list with a green indicator

If popup is blocked:

- Click "open auth page" link
- Complete authentication manually
- Return to inspector

### Connected Servers

Browse available resources:

- View resource descriptions
- Copy resource URIs
- Check MIME types
- Preview resource metadata

### Prompt Testing

Test prompts with the inspector:

1. Navigate to **Prompts** tab
2. Select a prompt
3. Fill in required arguments
4. Click **"Render"** to see output
5. Copy rendered prompt for use

---

## 🎨 UI Components

### Server Card

Each server displays:

- Connection status indicator
- Server name and URL
- Available tools count
- Action buttons: **Inspect**, **Disconnect**, **Remove**

### Tool Explorer

The tool explorer shows:

- Tool name and description
- Input schema with types
- Output schema
- Execution panel
- Response viewer with syntax highlighting

### Chat Interface

Interactive chat for testing conversational flows:

- Send messages to test prompts
- View tool calls in real-time
- See formatted responses
- Copy conversation history

---

## 🔍 Server Detail View

After clicking **"Inspect"** on a connected server, you'll see four main tabs:

### Tools Tab

The Tools tab displays all available tools from the MCP server.

**Features:**
- Browse all available tools with their names and descriptions
- Select a tool to view its detailed schema
- Click **"Execute"** to test the tool
- Enter JSON parameters in the input panel
- View real-time results with syntax highlighting
- Support for MCP-UI and OpenAI Apps SDK widgets

Sessions are automatically saved to localStorage:

- Preserves server configurations
- Maintains connection preferences
- Restores on page reload
- Clear with "Clear All Sessions"

### Resources Tab

The inspector respects system theme preferences:

- Light mode for better readability
- Dark mode for reduced eye strain
- Automatic switching based on OS settings

- View resource descriptions and metadata
- Copy resource URIs for use in your applications
- Check MIME types and resource properties
- Preview resource content

| Shortcut       | Action                  |
| -------------- | ----------------------- |
| `Cmd/Ctrl + K` | Quick server search     |
| `Cmd/Ctrl + N` | Add new server          |
| `Cmd/Ctrl + R` | Refresh all connections |
| `Esc`          | Close modals            |

---

## ⌨️ Keyboard Shortcuts

| Shortcut       | Action                     |
| -------------- | -------------------------- |
| `Cmd/Ctrl + K` | Quick search and navigation |
| `Esc`          | Close modals and overlays  |

```javascript
// Your MCP server
import { createMCPServer } from 'mcp-use/server'

const server = createMCPServer('dev-server', {
  version: '1.0.0',
  description: 'Development MCP Server',
})

server.tool('debug_tool', {
  description: 'Debug tool for testing',
  parameters: z.object({
    message: z.string(),
  }),
  execute: async ({ message }) => {
    console.log('Debug:', message)
    return { received: message, timestamp: Date.now() }
  },
})

server.listen(3000)
// Inspector at http://localhost:3000/inspector
```

### Production Server with Auth

```javascript
const server = createMCPServer('production-server', {
  version: '1.0.0',
  oauth: {
    clientId: process.env.OAUTH_CLIENT_ID,
    clientSecret: process.env.OAUTH_CLIENT_SECRET,
    authorizationUrl: 'https://api.example.com/oauth/authorize',
    tokenUrl: 'https://api.example.com/oauth/token',
  },
})

// Inspector handles OAuth flow automatically
```

### Multiple Server Management

In the inspector, manage multiple servers:

```javascript
// Add servers via UI
// Server 1: Local Development
URL: http://localhost:3000/mcp

// Server 2: Staging
URL: https://staging.example.com/mcp

// Server 3: Production
URL: https://api.example.com/mcp
```

---

## 💾 Persistency

The inspector automatically saves your configurations:

### Frontend Stack

- **React 19**: UI framework
- **React Router**: Navigation
- **Tailwind CSS**: Styling
- **shadcn/ui**: Component library
- **Framer Motion**: Animations
- **React Syntax Highlighter**: Code display

### Core Components

```
src/client/
├── components/
│   ├── InspectorDashboard.tsx  # Main dashboard view
│   ├── ServerList.tsx          # Server management
│   ├── ServerDetail.tsx        # Individual server view
│   ├── ToolExecutor.tsx        # Tool testing interface
│   ├── ResourceBrowser.tsx    # Resource explorer
│   └── ChatInterface.tsx      # Interactive chat
├── context/
│   └── McpContext.tsx         # Connection state management
└── hooks/
    └── useMcp.ts              # MCP connection hook
```

### Connection Management

The `useMcp` hook handles:

- WebSocket/SSE connections
- Automatic reconnection
- OAuth flow management
- Error recovery
- State synchronization

---

## 🐳 Self-Hosting

Deploy the MCP Inspector to your own infrastructure with a single Docker container. Perfect for enterprise environments, air-gapped networks, or when you need full control over your debugging environment.

### Docker Image

The official Docker image is available on [Docker Hub](https://hub.docker.com/r/mcpuse/inspector).

**Quick Start:**

**Inspector not loading:**

```bash
docker run -d -p 8080:8080 --name mcp-inspector mcpuse/inspector:latest
```

**Connection fails immediately:**

- Check CORS configuration
- Verify server URL is correct
- Ensure server supports SSE/WebSocket
- Check network/firewall settings

**OAuth popup blocked:**

- Allow popups for the inspector domain
- Use the manual auth link provided
- Check browser console for errors

**Tools not executing:**

- Verify tool schemas are valid
- Check server logs for errors
- Ensure proper authentication
- Validate input parameters

**Session not persisting:**

- Check localStorage is enabled
- Clear browser cache
- Try incognito/private mode
- Check for browser extensions blocking storage

---

## 📊 Telemetry & Privacy

The MCP Inspector collects anonymized usage data to help us improve the tool.

```javascript
// Use pagination for many tools
server.configurePagination({
  toolsPerPage: 50,
  enableSearch: true,
})
```

**Option 2: localStorage (Browser)**

```javascript
// Configure connection pooling
const inspector = {
  maxConnections: 5,
  connectionTimeout: 30000,
  keepAlive: true,
}
```

### Telemetry Providers

```javascript
// Cache tool results
server.enableCache({
  ttl: 300, // 5 minutes
  maxSize: 100, // MB
})
```

---

## 🔒 Security Considerations

### CORS Configuration

```javascript
// Configure CORS for inspector access
server.configureCORS({
  origin: ['http://localhost:3000'],
  credentials: true,
})
```

### Authentication

```javascript
// Add authentication middleware
server.use(authMiddleware)
```

### Rate Limiting

```javascript
// Prevent abuse
server.configureRateLimit({
  windowMs: 60000, // 1 minute
  max: 100, // requests
})
```

---

## 📚 API Reference

### Inspector Methods

```typescript
// Mount inspector
mountInspector(app: Express, path?: string): void

// Standalone server
startInspectorServer(port: number): void

// Configuration
configureInspector(options: InspectorOptions): void
```

### Connection Options

```typescript
interface InspectorOptions {
  autoConnect?: boolean // Auto-connect to local server
  theme?: 'light' | 'dark' | 'auto'
  persistence?: boolean // Save sessions
  maxConnections?: number
  connectionTimeout?: number
}
```

Both providers respect your privacy and follow GDPR compliance.
---

## 🤝 Contributing

We welcome contributions!

See our [contributing guide](https://github.com/mcp-use/mcp-use/blob/main/CONTRIBUTING.md) for details.

---

## 📚 Learn More

- [mcp-use Documentation](https://github.com/mcp-use/mcp-use-ts)
- [Model Context Protocol](https://modelcontextprotocol.io)
- [Creating MCP Servers](https://github.com/mcp-use/mcp-use-ts/tree/main/packages/mcp-use#-mcp-server-framework)
- [Building with React](https://react.dev)
- [Tailwind CSS](https://tailwindcss.com)

---

## 📜 License

MIT © [MCP-Use](https://github.com/mcp-use)
