# Block Get Look

**Category**: 🚀 Motion

![block_get_look thumbnail](https://portal.patchxr.io/block-thumbnails/block_get_look.png)

## Description

Outputs the angle (in degrees) between the origin block's right, up and forward axes and the direction towards the target. Useful to detect if the origin is facing or aligned with the target.

If multiple targets are connected, their average position is used as the direction reference. If no origin is connected, this block's own transform is used. Angle X uses the origin's right axis, Angle Y uses the up axis, Angle Z uses the forward axis. An angle of 0 means the axis points straight at the target; 90 means perpendicular; 180 means opposite.

## Related Wiki Pages

[player-inputs](/patching/player-inputs)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Origin | Tag Input | Block whose orientation is used as a reference. If left empty, this block's own transform is used. |
| Targets | Tag Input | Blocks pointed at by the origin. If multiple are connected, their average position is used. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Angle Z | Jolt Output | Angle (in degrees) between the origin's forward (Z) axis and the direction to the target. 0 means the origin is looking straight at the target. |
| Angle Y | Jolt Output | Angle (in degrees) between the origin's up (Y) axis and the direction to the target. |
| Angle X | Jolt Output | Angle (in degrees) between the origin's right (X) axis and the direction to the target. |

## Related Blocks

- [block_lookat](/blocks/motion/block_lookat)
- [block_get_rotation](/blocks/motion/block_get_rotation)
- [block_set_rotation](/blocks/motion/block_set_rotation)
- [block_relative_position](/blocks/motion/block_relative_position)
- [block_distance](/blocks/motion/block_distance)

---