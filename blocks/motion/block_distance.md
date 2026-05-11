# Get Distance

**Category**: 🚀 Motion

![block_distance thumbnail](https://portal.patchxr.io/block-thumbnails/block_distance.png)

## Description

Outputs the distance (in meters) between two blocks. Connect blocks to both Tag inputs; if either input is left unconnected, this block's own position is used as a reference.

Useful for proximity detection, gameplay triggers or to drive any value based on how far two objects are. If multiple blocks are connected to a single Tag input, their average position is used. The distance is recomputed automatically whenever a connection is added or removed.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Block A | Tag Input | First block (or group of blocks) used to measure the distance from. |
| Block B | Tag Input | Second block (or group of blocks) used to measure the distance to. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Distance | Jolt Output | Distance between Block A and Block B, in meters. |

## Related Blocks

- [block_relative_position](/blocks/motion/block_relative_position)
- [block_get_look](/blocks/motion/block_get_look)
- [block_lookat](/blocks/motion/block_lookat)
- [raycast](/blocks/controllers/raycast)
- [trigger_box](/blocks/players/trigger_box)

---