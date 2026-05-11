---
title: Variable System
description: Remotely reference other blocks
published: true
date: 2026-05-11T16:10:22.699Z
tags: 
editor: markdown
dateCreated: 2026-05-11T16:10:22.699Z
---

# Variable System

The Variable System lets you **attach named values to blocks at runtime** and later read them back, list them, or remove them. Think of it as a flexible "tagging" system that doubles as a key/value store: each variable is a name (e.g. `Score`, `Health`, `IsRocket`) paired with a double-precision number, attached to a specific block (or Group/Device).

Variables shine when your gameplay is **dynamic**: blocks are spawned, removed, or change role at runtime and you don't want (or can't) hard-wire Tag connections to every one of them.

---

## The blocks

- ![Set Variable small](https://portal.patchxr.io/block-thumbnails/set_variable.png =80x80) [Set Variable](/blocks/system/set_variable): attach (or update) a named variable on one or more blocks.
- ![Get Variable small](https://portal.patchxr.io/block-thumbnails/get_variable.png =80x80) [Get Variable](/blocks/system/get_variable): read the variable's value from a specific block.
- ![All With Variable small](https://portal.patchxr.io/block-thumbnails/all_with_variable.png =80x80) [All With Variable](/blocks/system/all_with_variable): output the list of every block currently tagged with a given variable. Supports value filtering and sorting.
- ![Remove Variable small](https://portal.patchxr.io/block-thumbnails/remove_variable.png =80x80) [Remove Variable](/blocks/system/remove_variable): detach the variable from blocks (or wipe it from every block at once).

All four blocks share a **Variable Name** text field (with auto-completion of names already in use in the world) and behave automatically by default: they re-evaluate themselves whenever an upstream input or value changes. Connect their **Manual Trigger** jolt input if you want to keep full control over when they fire.

---

## Storage model

Internally, every variable is a `(name, movableSubPart) -> double` entry. A few consequences:

- A block can carry **multiple variables** with different names at the same time.
- The same name can be reused across many blocks: `all_with_variable` is what you use to retrieve them all.
- Values are doubles, but you can repurpose them as booleans (0/1), enums (0,1,2...) or just markers (the value doesn't matter, only the presence of the variable does).
- Removing a block also removes all its variables.

---

## Local vs Global scope (the Restrict input)

By default a variable name is **global**: every `Set`, `Get`, `All With` and `Remove` block in the world that types the same name talks to the same registry. This is great for "world-wide" gameplay (a single Score per world, an `IsEnemy` tag, etc.) but not always what you want.

Imagine you build a **rifle** that stores the last hit plate as `LastHit`. If you copy/paste that rifle, both copies will overwrite the same `LastHit` and step on each other.

The **Restrict (Optional)** tag input solves this. Connect it to a Group or Device to scope the variable name to that subpatch. Internally, the variable is renamed to `<DevicePath>/<VariableName>`, so each copy of the rifle keeps its own `LastHit` even though you typed the same name on every block. The matching `Get Variable` / `All With Variable` / `Remove Variable` blocks must wire their own Restrict input to the same Group/Device.

In the inspector, you can also tick **Add restriction input** to reveal the Restrict tag input. When restricted, the variable name is rendered red on the block to make it obvious that the scope is local.

---

## Static reference vs Dynamic tagging

Patchworld already has Tag connections to reference blocks. The Variable System is **complementary**:

- Use a regular Tag connection when you have a **fixed, hand-wired** reference (e.g. one specific block to set the position of).
- Use Variables when the set of blocks evolves at runtime: things you spawn with [Block Spawn](/blocks/system/block_spawn), things you discover via collisions or raycasts, things you mark and unmark as gameplay progresses.

A common pattern is to combine both: store something dynamically with `Set Variable`, then list it with `All With Variable` and feed the result into a regular Tag input.

---

## Patterns & examples

### Tag spawned enemies

```
block_spawn ──► Set Variable "IsEnemy" = 1
              ▲
              └── (the spawn output is auto-fed into Set Variable's Input)

All With Variable "IsEnemy" ──► block_foreach ──► (apply set_color, set_position...)
```

Every newly-spawned enemy is automatically picked up by the rest of the patch.

### Per-player score

Use [Set Variable](/blocks/system/set_variable) on a [Players](/blocks/players/players)' Local Player or All Players output, with **Value is additive** ticked. Each hit/pickup adds to the score:

```
on_hit ──► Set Variable "Score" (additive) = 1, Input = local player
```

Then `All With Variable "Score"` with **Order in output: Descending** gives you a sorted leaderboard.

### Per-rifle "last hit"

Wrap your rifle into a Group/Device. On the rifle's `Set Variable "LastHit"`, tick **Add restriction input** and connect the rifle's own Group/Device to it. Now `Get Variable` (with the same Restrict) inside the rifle reads the right `LastHit` no matter how many copies of the rifle exist in the world.

### Storing lists of references

Even though the value type is "double", what really matters in many gameplay patches is the **presence** of the variable, not its value. You can use `Set Variable` purely as a "tag this block" action, and rely on `All With Variable` to retrieve the set, e.g. `KilledTargets`, `Inventory`, `OpenDoors`.

---

## Inspector options at a glance

| Block | Thumbnail | Option | Purpose |
| :--- | --- | :--- | :--- |
| `Set Variable` | | Value is additive | New value is added to the current value instead of overwriting. |
| `Set Variable` | | Add restriction input | Reveal the Restrict tag input to scope the variable to a Group/Device. |
| `Set Variable` | | Use Device on Input | Tag the parent Device of the input block instead of the block itself. |
| `Set Variable` | | Broadcast Multiplayer | Sync the change over the network via RPC. |
| `Get Variable` | | Add restriction input / Use Device on Input | Same scoping rules as Set. |
| `All With Variable` | | Add restriction input | Same scoping rule as Set. |
| `All With Variable` | | Value Filter | Keep only blocks whose variable equals a specific value. |
| `All With Variable` | | Order in output | Sort the output list by value (Ascending / Descending). |
| `Remove Variable` | | Remove on all blocks | Hide the Input and remove the variable from every block. |
| `Remove Variable` | | Also remove all Local | Also wipe every restricted (local) version of the same name. |

---

## Multiplayer notes

By default, variables are **local to each player**: every player has their own copy of the registry. To synchronize a value across the session, tick **Broadcast Multiplayer** on the relevant `Set Variable`. This sends an RPC that re-applies the same `(name, block, value)` on every other player. Variables on the local player part can also be broadcast (the receiver resolves the player rig automatically).

For values that should **persist across sessions** (high scores, player progress, who-visited-what), the Variable System is not enough — those live only in memory. Use [Online Variables](/wiki/online-variables) instead.
