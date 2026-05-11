# Saber

**Category**: 🎮 Controllers

![saber thumbnail](https://portal.patchxr.io/block-thumbnails/saber.png)

## Description

A grabbable lightsaber-style controller. Outputs the saber's movement, length and trigger state, and can play audio from its blade as a spatial speaker.

Grab the saber's handle and swing it. The block emits jolts for linear velocity, angular velocity, current blade length, whether it is held, and the controller trigger pressure. Connect a stream to the Audio input to make the blade sing — sound is emitted from the blade's position with spatial mix. Set the blade length and hue color via jolt inputs, or drag the extension handle to resize the blade manually.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Audio from Saber | Stream Input | Connect an audio stream here to play it from the saber's blade as a spatial speaker. |
| Haptic | Stream Input | Connect a stream here to drive constant-strength haptic vibration on the controller holding the saber. |
| Set Length | Jolt Input | Sets the blade length from a jolt. Clamped to 0-100 m. |
| Hue Color | Jolt Input with Dial | Sets the hue of the blade (0-1, wrapping around the color wheel). Affects the light, blade and trail colors. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Is Held | Jolt Output | Emits 1 when the saber is picked up and 0 when it is dropped. |
| Length | Jolt Output | Emits the current blade length (updated whenever the blade is resized). |
| Move Speed | Jolt Output | Emits the magnitude of the blade's linear velocity each frame. |
| Rotation Speed | Jolt Output | Emits the saber's angular velocity each frame (degrees per second). |
| Trigger Press | Jolt Output | Emits the controller trigger pressure (0 = released, 1 = fully pressed) while the saber is held. |

### Others

| Name | Type | Description |
|------|------|-------------|
| SaberObject | Interactible | The saber handle. Grab to hold the saber. |
| Blade Extend | Draggable part | Drag to change the blade length manually. |

## Related Blocks

- [speed](/blocks/motion/speed)
- [hapticcontrol](/blocks/players/hapticcontrol)
- [output](/blocks/audio/output)
- [string](/blocks/audio/string)

---