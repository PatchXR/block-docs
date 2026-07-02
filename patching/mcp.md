---
title: Connecting Patchworld MCP to AI Agents
description: Connect Patchworld MCP to Codex, ChatGPT, Claude Code, and other AI agents
published: true
date: 2026-07-02T00:45:12.807Z
tags: patching, mcp, patchworld
editor: markdown
dateCreated: 2026-05-27T23:49:20.480Z
---

# Connecting Patchworld MCP to AI Agents

The Patchworld MCP server lets AI agents inspect and edit your running Patchworld scene — spawning blocks, connecting them, and reading live state. Available in Patchworld 77.3 and up.

| | |
|---|---|
| **Server URL** | `https://api.patchxr.io/mcp` |
| **Transport** | Streamable HTTP |
| **Auth** | `Authorization: Bearer <YOUR_API_KEY>` |
| **API key** | [Patchworld Portal → Account](https://portal.patchxr.io/account) |

**Before connecting**, open the in-app console in Patchworld and run `agent_control on`. The agent controls whichever app instance is logged in with the same account that created the key. For the full tool list, see the [Tools Reference](tools.md).

> **Fastest setup:** send this page to your agent and ask it to configure Patchworld MCP for its client. Paste the key when it asks, or — better — put the key in an env var or a local file and give the agent that instead, so it never lands in chat history.

---

## Configure your client

Replace `<YOUR_API_KEY>` with your key in every snippet below.

### Claude Code
`~/.claude.json`
```json
"mcpServers": {
  "patchworld": {
    "type": "http",
    "url": "https://api.patchxr.io/mcp",
    "headers": { "Authorization": "Bearer <YOUR_API_KEY>" }
  }
}
```


### Google Antigravity
`~/.gemini/antigravity-cli/mcp_config.json`
```json
{
  "mcpServers": {
    "patchworld": {
      "serverUrl": "https://api.patchxr.io/mcp",
      "headers": { "Authorization": "Bearer <YOUR_API_KEY>" }
    }
  }
}
```

### OpenAI Codex
`~/.codex/config.toml` (or `<project>/.codex/config.toml`)
```toml
[mcp_servers.patchworld]
url = "https://api.patchxr.io/mcp"
bearer_token_env_var = "PATCHWORLD_API_KEY"
```
Set the env var, then restart Codex and run `/mcp` to confirm `patchworld` is listed:
```bash
export PATCHWORLD_API_KEY="<YOUR_API_KEY>"        # Windows: $env:PATCHWORLD_API_KEY="<YOUR_API_KEY>"
```
### Claude.ai (web)
**Settings → Connectors → Add custom connector.** Give it a name (e.g. `patchworld mcp`) and set the URL to `https://api.patchxr.io/mcp`. Leave **OAuth Client ID / Secret** blank — no manual key needed here. The server publishes OAuth Protected Resource Metadata, so Claude auto-discovers the auth server and registers itself via Dynamic Client Registration (RFC 7591). Click **Connect** and you'll be sent to a PatchWorld login page instead of pasting an API key; approve it and the connector activates. This is the same underlying flow ChatGPT's developer-mode connectors use, see below.

### ChatGPT web 
on ChatGPT web: **Settings → Apps & Connectors → Advanced → Developer mode**, then **Connectors → Create**, name it `PatchWorld Dev`, and use `https://api.patchxr.io/mcp`. Leave any token/secret field blank — ChatGPT auto-discovers the server's OAuth support and prompts you to log in with your PatchWorld account (same flow as Claude.ai below). Enable it from the **+** menu in a new chat.


### Your own client
The server is **Streamable HTTP** — use `StreamableHTTPClientTransport`, **not** the legacy `SSEClientTransport`. With SSE the client opens a stream and waits for an `endpoint` event that never comes, so it hangs with no error: **a connect timeout almost always means the wrong transport.** Auth is the `Authorization: Bearer` header only — no query params or `X-API-Key`.
```js
import { Client } from '@modelcontextprotocol/sdk/client/index.js';
import { StreamableHTTPClientTransport } from '@modelcontextprotocol/sdk/client/streamableHttp.js';

const client = new Client({ name: 'my-agent', version: '1.0.0' }, { capabilities: { tools: {} } });
await client.connect(new StreamableHTTPClientTransport(
  new URL('https://api.patchxr.io/mcp'),
  { requestInit: { headers: { Authorization: `Bearer ${process.env.PATCHWORLD_API_KEY}` } } }
));
console.log((await client.listTools()).tools.length, 'tools available');
```

---

## Troubleshooting

- **Connect hangs / times out** — wrong transport (custom clients: use Streamable HTTP, not SSE), or `agent_control on` wasn't run.
- **Tools don't appear** — run `agent_control publish` in the console, then refresh your client.
- **Calls hang after connecting** — make sure Patchworld is open and logged in with the same account that owns the key.
