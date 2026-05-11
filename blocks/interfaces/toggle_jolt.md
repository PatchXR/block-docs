# Toggle Jolt

**Category**: 🎚️ Interfaces

![toggle_jolt thumbnail](https://portal.patchxr.io/block-thumbnails/toggle_jolt.png)

## Description

A latching on/off switch. Click it or send a jolt to flip the state; emits 1 when on, 0 when off.

Useful for any binary state in a patch: mute/unmute, arm/disarm, enable a behavior, etc. The output fires every time the state changes (whether by click, by 'Toggle' input, or by 'Set state' input), and also reflects the current state when read.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Toggle | Jolt Input | Flips the state on every jolt received (any value). Use it for momentary buttons that should latch. |
| Set state | Jolt Input | Sets the state explicitly: any non-zero value turns it on, 0 turns it off. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the current state every time it changes: 1 when on, 0 when off. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Toggle switch | interactive | Press the trigger button on your controller to toggle the on/off state. |

## Related Blocks

- [toggle_new](/blocks/interfaces/toggle_new)
- [toggle](/blocks/interfaces/toggle)
- [button](/blocks/interfaces/button)
- [value](/blocks/interfaces/value)
- [trigger](/blocks/interfaces/trigger)

---