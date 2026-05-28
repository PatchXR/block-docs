---
title: Connecting Patchworld MCP to AI Agents
description: Updated Patchworld MCP Guide via script
published: true
date: 2026-05-28T00:11:48.428Z
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

### Other Clients
The Patchworld MCP server is compatible with any development tool or client that supports the Model Context Protocol (MCP). If you are using a different tool, you can simply ask your AI agent to help you connect it using the parameters provided in the configurations above.

