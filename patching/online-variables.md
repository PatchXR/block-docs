---
title: Online Variables
description: Send/Receive Text & Numbers to our server.
published: true
date: 2026-05-11T15:55:57.500Z
tags: 
editor: markdown
dateCreated: 2026-05-11T15:55:57.500Z
---

# Online Variables

Online Variables let you store and retrieve values on **Patchworld's server** so they persist across sessions, between worlds, and between players. Unlike the local [Variable System](/wiki/variable-system), values posted online are kept on the backend and can be read back from any other Patchworld session.

Typical use cases:

- World-wide leaderboards & high scores.
- Persistent player progress (XP, unlocked levels, settings).
- "Has visited my world?" flags, even when the player is currently playing **another** world.
- Storing per-player inventories or simple save data.

---

## The blocks

- ![Post Var small](https://portal.patchxr.io/block-thumbnails/post_variable.png =80x80) [Post Var](/blocks/system/post_variable) (*Post Var*): push a value (number or text) under a named key.
- ![Fetch Var small](https://portal.patchxr.io/block-thumbnails/fetch_variable.png =80x80) [Fetch Var](/blocks/system/fetch_variable) (*Fetch Var*): pull the latest value of a key back from the server.

Both blocks share three things:

1. A **Key** text input — the name of the variable on the server.
2. A **Value Type** dropdown (Number or Text) — switches the block between using the dial / jolt input or the text-blocks tag input.
3. A **Can be read from** dropdown — the **scope** that controls how the key is namespaced. Both ends (Post and Fetch) must use the same scope to talk to each other.

---

## Scopes

| Scope | What gets prefixed | Use for |
| :--- | :--- | :--- |
| **All Worlds** | Nothing — global key. | Cross-world data shared by everyone (e.g. a "has visited Patchworld" flag). |
| **All My Worlds** | Your **user id**. | Data shared between worlds you own (e.g. an account-wide currency). |
| **Only This World** | This world's **product id**. | Data scoped to a single world (e.g. this world's leaderboard). |

Internally, the prefix is added automatically before the request: a key typed `Score` in the *All My Worlds* scope becomes something like `<your_user_id>/Score` on the server. To read it back, `Fetch Var` must be set to the same scope so it builds the same prefix.

---

## Number vs Text

The **Value Type** dropdown chooses what kind of value is sent or received:

- **Number**: `Post Var` reads a value from its dial / jolt input and stores it as a number. `Fetch Var` emits the loaded number on its **Fetched Value** jolt output.
- **Text**: `Post Var` exposes a Tag input that accepts text-bearing blocks (e.g. *Txt*, *Get Name*, *Join & Apply Text*). Their text contents are concatenated and posted as a string. `Fetch Var` exposes a Tag input named *Text Output* — connect *Txt* blocks here and the fetched string is written into them when the request succeeds.

In both cases, the boolean *On Done* / *On Fail* outputs let you chain logic (e.g. show a "Saved!" message, or retry on failure).

---

## Per-player keys (the most useful pattern)

The keys themselves are just strings, so you can build them dynamically. By combining [Players](/blocks/players/players), [Get Name Text](/blocks/system/get_name) and [Join & Apply Text](/blocks/system/join_apply_text), you can produce per-player keys without any server-side concept of "user".

Pattern:

```
players (Local Player or All Players) ──► get_name ──┐
                                                     ├──► join_apply_text ──► Post Var "<PlayerID>/Score"
                                              "/Score" ──┘
```

Now every player writes to their own slot, and you can fetch any specific player's score from any world by reproducing the same key on a `Fetch Var`. The same trick lets you build:

- `<PlayerID>/HasVisitedMyWorld = 1` — to know if a given player has ever visited your world, even from another world.
- `<PlayerID>/Inventory` — text-mode keys are great for serializing a JSON-ish inventory blob.
- `<PlayerID>/HighScore` — combined with **All My Worlds** scope, you get a per-account high score that follows the player across all your worlds.

To rewrite the *Key* field at runtime (instead of typing it manually), use a [Join & Apply Text](/blocks/system/join_apply_text) block targeting the `Post Var` / `Fetch Var` block: it can compose the key from a player id and a static suffix and apply it programmatically.

---

## Rate limit

To keep the backend healthy and the experience snappy, both `Post Var` and `Fetch Var` enforce a **soft cap of 10 operations per 10 seconds** per block. If a request arrives over budget, it is **delayed** until the budget recovers (the *On Done* / *Fetched Value* / *On Fail* output fires whenever the request finally completes).

Practical consequences:

- Don't post on every audio frame — debounce with a [Delay Jolt](/blocks/logic/delay_jolt_2), a [Metronome](/blocks/logic/metronome) tick, or only on meaningful events (round end, pickup, save button...).
- For rapidly-changing values (a live position), keep them in the local [Variable System](/wiki/variable-system) and only post a snapshot occasionally.
- If you absolutely need bursts (e.g. saving a long inventory), spread the writes over time or batch them into a single text key.

---

## Examples

### Saving a high score

1. Build your gameplay locally with [Set Variable](/blocks/system/set_variable) `Score` (e.g. additive) on the local player.
2. On the *Game Over* event:
   - Use [Get Variable](/blocks/system/get_variable) to read the final `Score`.
   - Wire it into a `Post Var` with key `Score` (or `<PlayerID>/Score` for per-player), scope **Only This World**.
3. On *Game Start*:
   - Use a `Fetch Var` with the same key/scope.
   - Display the value with a *Number Readout* or *Txt* block.

### Cross-world "achievements"

Set a `Post Var` key `<PlayerID>/Achievements/FoundSecret = 1`, scope **All Worlds**. From any other world you make, a `Fetch Var` on the same key will return 1 if the player has unlocked the achievement, or trigger *On Fail* if they haven't.

### Persistent inventory

Use **Value Type: Text** on both `Post Var` and `Fetch Var`. Build the inventory string with [Join & Apply Text](/blocks/system/join_apply_text) and post it under `<PlayerID>/Inventory`. On world load, fetch it back into a *Txt* block and parse it however your gameplay needs.

---

## Online vs Local Variables

| Need | Use |
| :--- | :--- |
| Tag/list blocks dynamically inside a single play session | [Variable System](/wiki/variable-system) |
| Synchronize values between players in the same session | [Variable System](/wiki/variable-system) with **Broadcast Multiplayer** |
| Persist values **between** sessions, players, or worlds | **Online Variables** (this page) |

It's common to layer the two: keep gameplay state in local variables for speed, and only post/fetch the snapshot you actually want to persist.
