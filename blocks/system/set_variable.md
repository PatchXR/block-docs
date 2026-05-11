# Set Variable

**Category**: ⚙️ System

![set_variable thumbnail](https://portal.patchxr.io/block-thumbnails/set_variable.png)

## Description

Attach a named variable with a numeric value to one or more blocks. Use it to dynamically tag blocks (e.g. Score, Health, IsRocket) and later retrieve or filter them with "Get Variable" and "All With Variable".

Variables are stored as double-precision numbers, but you can also use them as boolean flags (0/1) or as a way to dynamically build lists of blocks (similar to "tagging" in other engines). Pair this block with "Get Variable", "All With Variable" and "Remove Variable" to make gameplay react to blocks that are spawned or removed at runtime, without needing to hard-wire Tag connections.

By default, variable names are global. Use the "Restrict" tag input (or the inspector toggle) to scope a variable to a specific Group/Device: this is essential when you copy-paste a setup (e.g. a rifle that stores its own "lastHit") so that each copy keeps its own value under the same name.

See the [Variable System](/wiki/variable-system) wiki page for more details and examples.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Variable Name | Text Input | Name of the variable to attach to the input blocks. Click to type a new name; if other Variable blocks already use names, they will be suggested. |
| Value | Jolt Input with Dial | Numeric value to assign to the variable on every connected block. |
| Input | Tag Input | Blocks we want to attach the variable to. |
| Restrict (Optional) | Tag Input | Connect a Group or Device to make the variable local to it. "Get Variable" and "All With Variable" must use the same Restrict input to read the value. Useful when copy-pasting a setup so each copy keeps its own variable under the same name. |
| Manual Trigger | Jolt Input | If connected: only assign the variable when this jolt fires. If not connected: the block triggers automatically whenever Input or Value changes. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Value is additive | checkbox | When ticked, the new value is added to the variable's current value (like a += operation) instead of overwriting it. Useful for accumulating scores, hit counts, or progress. |
| Add restriction input | checkbox | Reveals the "Restrict" tag input. When connected to a Group or Device, the variable becomes local to that scope and is only readable by Get Variable / All With Variable blocks that share the same restriction. |
| Use Device on Input | checkbox | When ticked and a block inside a Device is connected to the Input, the variable is attached to the parent Device instead of the inner block. |
| Broadcast Multiplayer | checkbox | Synchronizes the variable change to all other players in the multiplayer session via RPC. Leave off for purely local logic. |
| Edit text from outside | checkbox | When this block is placed inside a Group/Device, its text input is normally only editable from inside the group. Tick this option to let players still click and type into it from outside the group. |

## Related Blocks

- [get_variable](/blocks/system/get_variable)
- [all_with_variable](/blocks/system/all_with_variable)
- [remove_variable](/blocks/system/remove_variable)
- [block_foreach](/blocks/system/block_foreach)
- [post_variable](/blocks/system/post_variable)

---