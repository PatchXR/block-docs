# Haptic Control

**Category**: 👨‍👩‍👧‍👦 Players

![hapticcontrol thumbnail](https://portal.patchxr.io/block-thumbnails/hapticcontrol.png)

## Description

Vibrates the controllers at a set intensity. Connect a 0-1 value to control vibration strength for the right and left controllers independently.

Useful for adding tactile feedback to interactive patches, such as collision impacts, beat rhythms, or interactive surfaces. Optionally restrict haptics to a specific player using the Tag input.

## Related Wiki Pages

[player-inputs](/patching/player-inputs)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Haptics right | Stream Input | Right controller haptics |
| Haptics left | Stream Input | Left controller haptics |
| Restrict Player (optional) | Tag Input | You can restrict who will be receiving the haptics. example: connecting the "Nearest Player" output of the "Players" block. |

## Related Blocks

- [controloutput](/blocks/controllers/controloutput)
- [controllerrotation](/blocks/players/controllerrotation)
- [controllerposition](/blocks/players/controllerposition)
- [moveanalysis](/blocks/controllers/moveanalysis)

---