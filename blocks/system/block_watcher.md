# Block Watcher

**Category**: ⚙️ System

![block_watcher thumbnail](https://portal.patchxr.io/block-thumbnails/block_watcher.png)

## Description

Attach blocks via the Tag input and get jolts whenever players interact with them - hover, grab, hit, wire changes, stream-input edits and more.

A general-purpose interaction watcher. Connect any block(s) to the Tag input and each output emits when the corresponding event happens on one of the watched blocks. Useful for building reactive logic that responds to what players are doing without each block needing custom wiring. The 'Ignore ghosts' inspector setting (on by default) filters out events caused by ghost/recorded players.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Blocks to watch | Tag Input | Pull out the sticks to attach blocks. All outputs below report events that happen on any attached block. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Hover | Jolt Output | Emits a jolt when you start or stop hovering your controller over an attached block. |
| Grab | Jolt Output | Emits a jolt when you grab or release an attached block. |
| Hit | Jolt Output | Emits the velocity of the controller when you hit and attached block (if it's hittable). |
| Marble | Jolt Output | Emits the velocity of the marble when an attached block gets hit by a marble (if it supports marble hits). |
| Wire created | Jolt Output | Emits the index of the jolt output a player just connected a wire from, on an attached block. |
| Wire removed | Jolt Output | Emits the index of the jolt output a player just disconnected a wire from, on an attached block. |
| Jolt connected | Jolt Output | Emits the index of the jolt input that just had a wire connected to it, on an attached block. |
| Jolt disconnected | Jolt Output | Emits the index of the jolt input that just had a wire disconnected from it, on an attached block. |
| Stream input index | Jolt Output | Emits the index of a stream input whose value just changed on an attached block. Pair with 'Stream input value' to know which dial was edited. |
| Stream input value | Jolt Output | Emits the new value of a stream input that was just edited on an attached block. |
| Stream input hover | Jolt Output | Emits the index of a stream input when a player's controller starts hovering it on an attached block. |
| Bubble open | Jolt Output | Emits the current open progress (0 to 1) when an attached Bubble sample block is opened or closed. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Ignore ghosts | checkbox | When enabled (default), interactions performed by ghosts (recorded/looper players) don't fire the outputs - only live players do. |

## Related Blocks

- [scene_watcher](/blocks/system/scene_watcher)
- [trigger_box](/blocks/players/trigger_box)
- [block_foreach](/blocks/system/block_foreach)
- [block_list](/blocks/system/block_list)
- [block_spawn](/blocks/system/block_spawn)

---