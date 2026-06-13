---
title: In-App AI Agent
description: Built-in AI agent (agent console command): build and edit patches by asking
published: true
date: 2026-06-13T01:14:22.163Z
tags: 
editor: markdown
dateCreated: 2026-06-13T01:14:22.163Z
---

# In-App AI Agent

Patchworld includes a built-in AI agent you can talk to directly from the in-app console. The agent sees a snapshot of your current world and selection, and can build and edit patches for you — spawning blocks, connecting them, setting values, grouping devices and more — using the same tool set that powers the [Patchworld MCP](/en/patching/mcp).

To use it, open the in-app console and make sure you are **logged in** to your Patchworld account.

> Prefer talking instead of typing? See the [Live Voice Agent](/en/patching/live-agent) for a realtime voice conversation with the agent.

---

## `agent` — talk to the agent

```
agent "make a simple synth with an oscillator and a filter"
```

Sends your request to the agent. The conversation is **stateful** (kept on the server), so follow-ups remember earlier context:

```
agent "now connect a keyboard to it"
```

While the agent works, its tool calls and progress are streamed to the console. The agent operates in the scope you are currently standing in (the world, or the device you are inside).

---

## Companion commands

| Command | What it does |
|---|---|
| `agent_stop` | Stop **all** running agent sessions for your account — including sub-agents started by the [Live Voice Agent](/en/patching/live-agent). |
| `agent_reset` | Clear the conversation history and start fresh. |
| `agent_mode [verbose\|minimal]` | How much world context is sent with each request. `minimal` (default) sends a basic snapshot; `verbose` includes detailed object info. Run without an argument to print the current mode. |
| `agent_model [model]` | Switch the model. Shortcuts: `flash` (default — fast) and `pro` (more capable, slower). Run without an argument to list the available models. Changing the model resets the session. |
| `agent_system [text\|clear]` | Override the system prompt for the agent. |
| `agent_control [on\|off\|status]` | Allow or block **external** agents (MCP) from controlling this device. |

### `agent_system`

By default the system prompt is supplied by the server. You can override it per device:

```
agent_system "You only build drum machines. Refuse everything else."
```

- No argument — show the current override (if any).
- `agent_system <text>` — set an override; it is sent with every request until cleared.
- `agent_system clear` (also `default`, `none`, `off`) — remove the override and return to the server default.

### `agent_control`

This is the on-device gate for **external** control — for example when connecting AI clients through the [Patchworld MCP server](/en/patching/mcp):

```
agent_control on
```

- `on` / `enable` — allow external agents to control this device.
- `off` / `disable` — block external control.
- `status` (or no argument) — print whether external control is currently enabled.

---

## Examples

```
agent "list everything in this world"
agent "build a techno kick pattern at 130 bpm"
agent "connect the keyboard to the oscillator pitch"
agent_mode verbose
agent_model pro
agent "redesign this patch to be playable with one hand"
agent_stop
```
