# Progress Toggle

**Category**: 🎚️ Interfaces

![custom_toggle thumbnail](https://portal.patchxr.io/block-thumbnails/custom_toggle.png)

## Description

Tap to toggle off/on state, sending 0 or 1 from the Jolt output. Includes a circular progress indicator on the button face.

Useful for loop or play buttons where you want to visualize the progress of a loop or animation directly on the button.

To show the on/off state on the progress ring simply connect the Jolt out to the Progress input. To drive the progress indicator with another value (e.g. tempo phase), patch any 0 to 1 jolt to the Progress input.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Toggle State | Jolt Input | Send 0 or 1 to set and trigger the pressed or unpressed state. |
| Progress | Jolt Input | Fills up a circular progress indicator from 0 to 1. When 0 is received the indicator is empty, when 1 the indicator is full. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Jolt Out | Jolt Output | Emits 0 or 1 depending on the pressed or unpressed state. |

## Related Blocks

- [toggle_new](/blocks/interfaces/toggle_new)
- [toggle_jolt](/blocks/interfaces/toggle_jolt)
- [play_button](/blocks/interfaces/play_button)
- [button](/blocks/interfaces/button)

---