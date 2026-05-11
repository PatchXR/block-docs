# Controller Rotation

**Category**: 🎮 Controllers

![controllerrotation thumbnail](https://portal.patchxr.io/block-thumbnails/controllerrotation.png)

## Description

Outputs the Euler rotation angles (0-359 degrees) of both controllers along their X, Y, and Z axes.

## Related Wiki Pages

[player-inputs](/patching/player-inputs)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| X Rotation Right | Jolt Output | Emits the rotation of the right controller around the X axis, in degrees (0-359 range). |
| Y Rotation Right | Jolt Output | Emits the rotation of the right controller around the Y axis, in degrees (0-359 range). |
| Z Rotation Right | Jolt Output | Emits the rotation of the right controller around the Z axis, in degrees (0-359 range). |
| X Rotation Left | Jolt Output | Emits the rotation of the left controller around the X axis, in degrees (0-359 range). |
| Y Rotation Left | Jolt Output | Emits the rotation of the left controller around the Y axis, in degrees (0-359 range). |
| Z Rotation Left | Jolt Output | Emits the rotation of the left controller around the Z axis, in degrees (0-359 range). |

## Related Blocks

- [controloutput](/blocks/controllers/controloutput)
- [controllerposition](/blocks/players/controllerposition)
- [moveanalysis](/blocks/controllers/moveanalysis)
- [hapticcontrol](/blocks/players/hapticcontrol)

---