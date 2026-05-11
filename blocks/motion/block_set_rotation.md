# Set Rotation

**Category**: 🚀 Motion

![block_set_rotation thumbnail](https://portal.patchxr.io/block-thumbnails/block_set_rotation.png)

## Description

Sets the rotation of the "Target" block(s) using X, Y and Z Euler angles (in degrees). Connect an optional "Origin" block to express the rotation relative to it instead of the world.

Useful to align, snap or animate the rotation of blocks. Multiple targets can be connected; they all receive the same rotation. When an origin is connected, the angles are added on top of the origin's rotation.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Origin (optional) | Tag Input | Reference block. When connected, the target's rotation is set relative to this block. |
| Target | Tag Input | Block(s) whose rotation will be set. |
| X | Jolt Input with Dial | Rotation around the X axis (pitch), in degrees. |
| Y | Jolt Input with Dial | Rotation around the Y axis (yaw), in degrees. |
| Z | Jolt Input with Dial | Rotation around the Z axis (roll), in degrees. |

## Related Blocks

- [block_get_rotation](/blocks/motion/block_get_rotation)
- [block_lookat](/blocks/motion/block_lookat)
- [block_set_position](/blocks/motion/block_set_position)
- [block_set_scale](/blocks/visual/block_set_scale)
- [block_follow](/blocks/motion/block_follow)

---