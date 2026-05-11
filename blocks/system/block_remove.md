# Block Remove

**Category**: ⚙️ System

![block_remove thumbnail](https://portal.patchxr.io/block-thumbnails/block_remove.png)

## Description

Removes the blocks connected to its tag input when the Remove jolt fires. A delay can be set so the removal happens N seconds later.

Useful to clean up spawned content (paired with [block_spawn](/blocks/system/block_spawn)), to remove a block as soon as a condition is met (game over, target hit), or to time-out floating UI/VFX. Connect the blocks to delete via the Tag input, then fire the Remove jolt; the Delay knob/jolt controls how long Patchworld waits before actually destroying them. Permanent scene blocks (those marked as scene-persistent) are never removed.

With "Use Device on Input" enabled, connecting a block that lives inside a Device removes the whole parent Device instead of just the inner block, which is often what you want when you cloned a full Device with Block Spawn.

## Related Wiki Pages

[dynamic-patching](/patching/dynamic-patching)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Tag Input | Block(s) to remove when the Remove jolt fires. |
| Remove | Jolt Input | Triggers the removal of the connected blocks. The delay set by the Delay knob/jolt is applied before they actually disappear. |
| Delay | Jolt Input with Dial | Time (in seconds) between the Remove trigger and the actual removal of the blocks. 0 removes them immediately on the next tick. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Use Device on Input | checkbox | When ON and a block inside a Device is connected to the Input, the whole parent Device is removed instead of just the inner block. Handy when cleaning up Devices spawned with [block_spawn](/blocks/system/block_spawn). |

## Related Blocks

- [block_spawn](/blocks/system/block_spawn)
- [block_foreach](/blocks/system/block_foreach)
- [block_compare](/blocks/system/block_compare)
- [set_active](/blocks/system/set_active)
- [set_visible](/blocks/system/set_visible)
- [remove_variable](/blocks/system/remove_variable)

---