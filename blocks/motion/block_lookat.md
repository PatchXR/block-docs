# Set Look At

**Category**: 🚀 Motion

![block_lookat thumbnail](https://portal.patchxr.io/block-thumbnails/block_lookat.png)

## Description

Rotates the connected "Subjects" blocks to face the "Targets" blocks. Speed sets how fast they turn (in degrees per second). An optional "Up" Tag input lets you point a different axis as up.

Useful for cameras, NPCs, props or weapons that need to track a moving target smoothly. If multiple subjects are connected they all rotate; if multiple targets are connected, their average position is used. Set Speed to 0 to freeze rotation.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Subjects | Tag Input | Blocks that will rotate to face the targets. |
| Targets | Tag Input | Blocks that the subjects will face. If multiple are connected, their average position is used. |
| Up (optional) | Tag Input | Optional reference used to define the up axis of the subjects when looking at the targets. |
| Speed | Jolt Input with Dial | Rotation speed in degrees per second. 0 freezes the rotation. |

## Related Blocks

- [block_set_rotation](/blocks/motion/block_set_rotation)
- [block_get_look](/blocks/motion/block_get_look)
- [block_get_rotation](/blocks/motion/block_get_rotation)
- [block_follow](/blocks/motion/block_follow)
- [block_set_position](/blocks/motion/block_set_position)

---