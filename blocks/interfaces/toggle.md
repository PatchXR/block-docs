# Stream_switch

**Category**: 🎚️ Interfaces

![toggle thumbnail](https://portal.patchxr.io/block-thumbnails/toggle.png)

## Description

Click the switch to flip its state between off (0) and on (1). The state is exposed as a stream output.

Commonly used as an on/off switch for gates, multipliers, mute controls, or any boolean flag in a patch. Send a jolt to the Change State input to flip the switch from anywhere in the world.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Change State | Jolt Input | Any jolt coming in will flip the switch's current state. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| State Out (0/1)  | Stream Output | Continuous stream of 0 (off) or 1 (on) depending on the current state of the switch. |

## Related Blocks

- [toggle_new](/blocks/interfaces/toggle_new)
- [toggle_jolt](/blocks/interfaces/toggle_jolt)
- [custom_toggle](/blocks/interfaces/custom_toggle)
- [gate](/blocks/logic/gate)
- [button](/blocks/interfaces/button)
- [pad](/blocks/interfaces/pad)

---