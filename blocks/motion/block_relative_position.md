# Get Position

**Category**: 🚀 Motion

![block_relative_position thumbnail](https://portal.patchxr.io/block-thumbnails/block_relative_position.png)

## Description

Outputs the X, Y and Z position of the connected "Target" block. By default the position is local to this block; connect an "Origin" block to get the position relative to that one instead.

If multiple targets are connected, their average position is used. The output is recomputed every time the target moves. Use the inspector options to ignore the origin's rotation or scale, or to fall back to world space when no origin is connected.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Origin (optional) | Tag Input | Reference block. When connected, the output position is expressed relative to this block. |
| Target | Tag Input | Block whose position will be measured. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| X | Jolt Output | Position along the X axis (left/right), in meters. |
| Y | Jolt Output | Position along the Y axis (down/up), in meters. |
| Z | Jolt Output | Position along the Z axis (back/front), in meters. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Ignore Origin's Rotation | checkbox | Output the position in world axes, ignoring how the origin block is rotated. |
| Ignore Origin's Scale | checkbox | Output the position without dividing by the origin block's scale. |
| No Origin: use World Space | checkbox | When no origin is connected, output the world space position instead of the position local to this block. |

## Related Blocks

- [block_set_position](/blocks/motion/block_set_position)
- [block_distance](/blocks/motion/block_distance)
- [block_get_rotation](/blocks/motion/block_get_rotation)
- [block_get_look](/blocks/motion/block_get_look)
- [block_lookat](/blocks/motion/block_lookat)

---