---
title: Live Voice Agent
description: Realtime voice conversation with the AI agent (live console command)
published: true
date: 2026-06-13T01:14:26.001Z
tags: 
editor: markdown
dateCreated: 2026-06-13T01:14:26.001Z
---

# Live Voice Agent

The `live` command starts a **realtime voice conversation** with the Patchworld AI agent: speak through your microphone, and the agent answers out loud while it inspects and edits your patch. For big or complex jobs it can hand work off ("delegate") to the more capable main agent — the same one behind the [`agent` command](/en/patching/agent).

To use it, open the in-app console and make sure you are **logged in** to your Patchworld account.

---

## Subcommands

| Command | What it does |
|---|---|
| `live start [voice] [options]` | Start a full voice session (mic capture + audio playback). The optional first word is the voice name, e.g. `live start Puck`. |
| `live voice ...` | Alias for `live start`. |
| `live test ["prompt"] [options]` | Start a **text-only** session for testing (no mic). Auto-sends the prompt, or `"Say hello."` if none is given. |
| `live text "<message>"` | Send a text turn into the active session. Alias: `live say`. |
| `live interrupt` | Barge-in: stop the agent's current speech playback. Alias: `live barge`. |
| `live stop` | End the session. Alias: `live end`. |
| `live status` | Print the current session state and usage help. |

---

## Options

Options are `key=value` pairs that can be appended to `live start` / `live test` and combined freely. Use quotes for values with spaces.

```
live start voice=Aoede tools=read_only
live test "what is in front of me?" system="Answer in rhymes." systemMode=append
```

| Option | Values | Default | Description |
|---|---|---|---|
| `voice=` | A Gemini Live voice name, e.g. `Kore`, `Puck`, `Charon`, `Fenrir`, `Aoede` | `Kore` | The voice the agent speaks with. |
| `model=` | A live-capable model id | `gemini-3.1-flash-live-preview` | The realtime model running the voice session. |
| `system=` | Any text (quoted) | Server default | Custom system prompt for the session. Aliases: `prompt=`, `instruction=`. |
| `systemMode=` | `server` \| `append` \| `replace` | `replace` when `system=` is set, otherwise `server` | How your custom prompt combines with the server's built-in policy: keep the server prompt, append yours to it, or fully replace it. |
| `tools=` | `default` \| `read_only` \| `custom` \| `none` | `default` | Which tool set the voice agent gets. `read_only` allows inspection only (no edits); `custom` uses exactly the tools in `allow=`; `none` disables direct tools. |
| `allow=` | Comma-separated tool names | — | The allowed tool list when `tools=custom`. |
| `block=` | Comma-separated tool names | — | Tools removed from the resolved set, in any tool mode. |
| `delegation=` | `enabled` \| `disabled` \| `private_only` \| `visible_only` | `enabled` (`disabled` when `tools=none`) | Whether the voice agent may hand work to the more capable agent, and whether those answers appear in the app (visible) or stay as private advice to the voice agent. |
| `delegateModel=` | A model id | `gemini-3.1-pro-preview` | The model used for delegated work. |
| `modalities=` | `audio`, `text` (comma-separated) | `audio` | The response modalities of the session. |

---

## Delegation

The live voice model is optimized for speed, not deep reasoning. When you ask for something complex — a broad patch design, a long multi-step build — it delegates the task to the **more capable agent** and keeps talking with you while that agent works in the background. You can ask it at any time what the delegated agent is doing or whether it is done.

- **Visible** delegation shows the full answer in the app; **private** delegation returns the result only to the voice agent, which then summarizes it out loud.
- Control this with the `delegation=` option above.
- To cancel everything — the voice session's sub-agents included — run [`agent_stop`](/en/patching/agent).

---

## Session limits

Live sessions have a server-side time limit. Shortly before it is reached, the agent gets a heads-up so it can tell you the session is about to end, and the session then closes automatically. Just run `live start` again to continue.

---

## Examples

```
live start
live start Puck
live start voice=Aoede tools=read_only
live test
live test "list the blocks near me"
live text "make the filter brighter"
live interrupt
live stop
```
