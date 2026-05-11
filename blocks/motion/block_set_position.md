# Set Position

**Category**: 🚀 Motion

![block_set_position thumbnail](https://portal.patchxr.io/block-thumbnails/block_set_position.png)

## Description

Sets the position of the "Target" block(s) using X, Y and Z values. Connect an optional "Origin" block to position the targets relative to it instead of relative to this block.

Useful to teleport, align or animate blocks at given coordinates. Multiple targets can be connected; they will all be moved to the same position. Use the inspector options to ignore the origin's rotation or scale, or to fall back to world space when no origin is connected.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Origin (optional) | Tag Input | Reference block. When connected, the target's position is set relative to this block. |
| Target | Tag Input | Block(s) whose position will be set. |
| X | Jolt Input with Dial | Position along the X axis (left/right), in meters. |
| Y | Jolt Input with Dial | Position along the Y axis (down/up), in meters. |
| Z | Jolt Input with Dial | Position along the Z axis (back/front), in meters. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Ignore Origin's Rotation | checkbox | Apply the X, Y, Z values along world axes, ignoring how the origin block is rotated. |
| Ignore Origin's Scale | checkbox | Apply the X, Y, Z values without scaling them by the origin block's scale. |
| No Origin: use World Space | checkbox | When no origin is connected, interpret the X, Y, Z values as world space coordinates instead of values relative to this block. |

## Related Blocks

- [block_relative_position](/blocks/motion/block_relative_position)
- [block_set_rotation](/blocks/motion/block_set_rotation)
- [block_set_scale](/blocks/visual/block_set_scale)
- [block_follow](/blocks/motion/block_follow)
- [block_lookat](/blocks/motion/block_lookat)

---