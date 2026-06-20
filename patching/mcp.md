---
title: Connecting Patchworld MCP to AI Agents
description: Connect Patchworld MCP to Codex, ChatGPT, Claude Code, and other AI agents
published: true
date: 2026-06-20T00:00:00.000Z
tags: patching, mcp, patchworld
editor: markdown
dateCreated: 2026-05-27T23:49:20.480Z
---

# Connecting Patchworld MCP to AI Agents

The Patchworld Model Context Protocol (MCP) server enables AI agents to interact directly with the Patchworld app. This allows agents to perform complex, contextual actions such as spawning entities, connecting blocks, and querying real-time state information.

You can use the MCP server to control any instance of the Patchworld app running on any device, as long as it is logged in with the same user account that generated the API key in the portal.

To allow external connections on your device, open the in-app console in the Patchworld app and run:
```
agent_control on
```

To see the full capabilities and available tools, refer to the [Tools Reference](tools.md) page.

<div style="border: 1px solid #2dd4bf; border-left: 6px solid #2dd4bf; border-radius: 10px; padding: 18px 20px; margin: 24px 0; background: rgba(45, 212, 191, 0.10);">
  <div style="font-size: 0.82rem; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; color: #5eead4; margin-bottom: 8px;">Recommended setup</div>
  <p style="margin: 0 0 12px 0;"><strong>Fastest setup:</strong> copy this page and send it to the AI agent you want to use. Ask the agent to set up Patchworld MCP for its own client, then share your Patchworld API key with that agent when it needs to configure the connection.</p>
  <p style="margin: 0 0 12px 0; opacity: 0.82; font-size: 0.94rem;">For a cleaner setup, especially with coding agents, save the API key in a temporary local text file or environment variable and give the agent that file path or variable name instead of pasting the key into the chat.</p>
  <p style="margin: 0 0 8px 0;"><strong>Smooth copy-paste prompt:</strong></p>
  <pre style="white-space: pre-wrap; overflow-x: hidden; margin: 0; padding: 14px 16px; border-radius: 8px; background: rgba(0, 0, 0, 0.32); font-size: 0.92rem;"><code>Please set up Patchworld MCP for your client using this guide.
My MCP server URL is: https://api.patchxr.io/mcp
My Patchworld API key is:
&lt;YOUR_BEARER_TOKEN&gt;

Use it only to configure the MCP Authorization bearer token or environment variable.
Tell me when the Patchworld tools are available.
Do not print the API key back to me.</code></pre>
</div>

---

## 1. Obtaining an API Key
To connect an AI client to the Patchworld MCP server, you will need a Patchworld API key (Bearer token). 

You can easily generate and manage your API keys directly from the Patchworld portal:
* 🌐 **[Patchworld Portal — Account Settings](https://portal.patchxr.io/account)**

Once generated, save your token securely. You will use it in place of `<YOUR_BEARER_TOKEN>` in the configurations below.

---

## 2. Configuration for Supported AI Clients
Configure the Patchworld MCP server under the appropriate configuration file for your AI client. Make sure to replace `<YOUR_BEARER_TOKEN>` with your actual authorization key.

### Claude Code
Claude Code manages global MCP servers in the user-level configuration file:
* **Link:** [Claude Code MCP documentation](https://docs.anthropic.com/en/docs/claude-code/mcp)
* **File Location:** `~/.claude.json`
* **Configuration:**
  ```json
  "mcpServers": {
    "patchworld": {
      "type": "http",
      "url": "https://api.patchxr.io/mcp",
      "headers": {
        "Authorization": "Bearer <YOUR_BEARER_TOKEN>"
      }
    }
  }
  ```

### Google Antigravity
Google Antigravity CLI manages global MCP servers in its global configuration file:
* **Link:** [Google Antigravity MCP integration](https://antigravity.google/docs/mcp)
* **File Location:** `~/.gemini/antigravity-cli/mcp_config.json`
* **Configuration:**
  ```json
  {
    "mcpServers": {
      "patchworld": {
        "serverUrl": "https://api.patchxr.io/mcp",
        "headers": {
          "Authorization": "Bearer <YOUR_BEARER_TOKEN>"
        }
      }
    }
  }
  ```

### OpenAI Codex
Codex stores MCP server settings in `config.toml`. The Codex app, Codex CLI, and Codex IDE extension share this configuration.

* **Link:** [OpenAI Codex MCP documentation](https://developers.openai.com/codex/mcp)

You can configure Patchworld globally:
* **File Location:** `~/.codex/config.toml`

Or per project, if the project is trusted:
* **File Location:** `<your-project>/.codex/config.toml`

Add this configuration:
```toml
[mcp_servers.patchworld]
url = "https://api.patchxr.io/mcp"
bearer_token_env_var = "PATCHWORLD_API_KEY"
```

Then set the environment variable before starting Codex:

**macOS / Linux**
```bash
export PATCHWORLD_API_KEY="<YOUR_BEARER_TOKEN>"
```

**Windows PowerShell**
```powershell
$env:PATCHWORLD_API_KEY="<YOUR_BEARER_TOKEN>"
```

Restart Codex after editing the config. In the Codex CLI or TUI, run:
```bash
/mcp
```

You should see `patchworld` listed as an available MCP server. In the Codex app or IDE extension, open the MCP settings panel to confirm the server is enabled.

Once connected, ask Codex to inspect or edit your running Patchworld scene, for example:
```text
Use Patchworld to list the objects in my current scene.
```

### ChatGPT web temporary workaround
The official PatchWorld ChatGPT app has been submitted and is currently pending review. Until it is approved and available in ChatGPT, you can use ChatGPT developer mode to create your own temporary development connector.

This workaround is intended for testing and personal use from ChatGPT web.

* **Links:** [ChatGPT Apps quickstart](https://developers.openai.com/apps-sdk/quickstart), [Connect an MCP server from ChatGPT](https://developers.openai.com/apps-sdk/deploy/connect-chatgpt)

1. Open ChatGPT web.
2. Go to **Settings -> Apps & Connectors -> Advanced settings**.
3. Enable **Developer mode**.
4. Go to **Settings -> Connectors**.
5. Click **Create**.
6. Name the connector `PatchWorld Dev`.
7. Use this MCP server URL:
   ```text
   https://api.patchxr.io/mcp
   ```
8. If ChatGPT asks for authentication, complete the Patchworld authorization flow. If the developer connector offers a bearer-token or API-key field, paste your Patchworld API key there. Do not paste API keys into normal chat messages.
9. Create the connector.
10. Start a new chat, click the **+** / tools menu, enable `PatchWorld Dev`, and ask ChatGPT to use Patchworld.

Example prompt:
```text
Use PatchWorld to inspect my current scene and tell me what objects are connected.
```

Keep Patchworld open and run `agent_control on` in the in-app console before using the connector. If tools do not appear or calls time out, run:
```text
agent_control publish
```

Then refresh the connector metadata in ChatGPT developer settings.

### Other Clients
The Patchworld MCP server is compatible with any development tool or client that supports the Model Context Protocol (MCP). If you are using a different tool, you can simply ask your AI agent to help you connect it using the parameters provided in the configurations above.
