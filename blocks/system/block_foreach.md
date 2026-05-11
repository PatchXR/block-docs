# Block Foreach

**Category**: ⚙️ System

![block_foreach thumbnail](https://portal.patchxr.io/block-thumbnails/block_foreach.png)

## Description

Iterates over the blocks connected to its Input and re-emits each one through the "Output block" tag, paired with its Index. Use it together with blocks like Set Position, Set Color or Set Variable to apply per-block logic to a dynamic list.

Each iteration re-uses the same single Tag output: it disconnects the previous block, then connects the next one and fires the Index jolt. Connect the Output block to a block that reacts to its Tag input changing (Set Position, Set Color, Set Variable, Block Compare, Get Variable...) to apply different logic per block based on the index.

When the Trigger jolt input is **not** connected and "Trigger Automatically" is enabled, the loop runs every time the Input list changes. Wire the Trigger jolt to control execution manually. The Interrupt jolt input stops the current loop early; combine it with Compare/If to leave the Output on a specific block (e.g. find the first match).

A classic pattern is **[block_spawn](/blocks/system/block_spawn) → block_foreach**: connect the spawn block's "All copies" tag output into the foreach Input, trigger the foreach after each spawn, and use the Index to give each instance unique parameters.

See the [Dynamic Patching](/wiki/dynamic-patching) wiki page for end-to-end examples.

## Related Wiki Pages

[dynamic-patching](/patching/dynamic-patching) • [variable-system](/patching/variable-system)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input blocks | Tag Input | List of blocks to iterate over. The foreach loop will visit them in connection order. |
| Trigger | Jolt Input | Starts the foreach loop. If left unconnected and "Trigger Automatically" is on, the loop runs whenever the Input list changes. |
| Interrupt | Jolt Input | Stops the current loop early. The Output block stays connected to the last visited block, which is handy to "find" a specific block by index or condition. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output block | Tag Output | Tag output that re-emits each input block one at a time during the loop. Connect it to any Tag input that should react per-iteration. |
| Index | Jolt Output | Fires right after Output block is updated, with the index of the current block in the Input list (starting at 0). |
| Block count | Jolt Output | Fired once at the start of the loop with the total number of blocks that are about to be iterated. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Execute Continuously | toggle | When ON, the loop is re-run every frame regardless of whether the Input list or the Trigger jolt changed. Useful for visualizations that depend on per-frame state, but expensive on long lists. |
| Trigger Automatically | toggle | When ON and no jolt is connected to the Trigger input, the loop runs automatically every time the Input list changes. Turn OFF to keep full control of when the foreach fires. |
| Limit To Once a Frame | toggle | Caps the loop to a single execution per frame even if multiple Trigger jolts fire. Prevents runaway recursion when the foreach feeds back into itself indirectly. |

## Related Blocks

- [block_spawn](/blocks/system/block_spawn)
- [block_compare](/blocks/system/block_compare)
- [block_remove](/blocks/system/block_remove)
- [all_with_variable](/blocks/system/all_with_variable)
- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)
- [get_name](/blocks/system/get_name)
- [raycast](/blocks/controllers/raycast)

---