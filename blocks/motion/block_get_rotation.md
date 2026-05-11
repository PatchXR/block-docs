# Block Get Rotation

**Category**: 🚀 Motion

![block_get_rotation thumbnail](https://portal.patchxr.io/block-thumbnails/block_get_rotation.png)

## Description

Outputs the X, Y and Z Euler angles (in degrees) of the connected "Target" block. Connect an optional "Origin" block to express the rotation relative to it instead of the world.

Useful to read the orientation of a block and feed it into logic, audio or visual blocks. If multiple targets are connected, the average of their Euler angles is output. The output is recomputed every time a connection is added or removed.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Origin (optional) | Tag Input | Reference block. When connected, the output rotation is expressed relative to this block. |
| Target | Tag Input | Block whose rotation will be measured. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| X | Jolt Output | Rotation around the X axis (pitch), in degrees. |
| Y | Jolt Output | Rotation around the Y axis (yaw), in degrees. |
| Z | Jolt Output | Rotation around the Z axis (roll), in degrees. |

## Related Blocks

- [block_set_rotation](/blocks/motion/block_set_rotation)
- [block_get_look](/blocks/motion/block_get_look)
- [block_relative_position](/blocks/motion/block_relative_position)
- [block_lookat](/blocks/motion/block_lookat)
- [block_distance](/blocks/motion/block_distance)

---