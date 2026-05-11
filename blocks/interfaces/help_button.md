# Button Help

**Category**: 🎚️ Interfaces

![help_button thumbnail](https://portal.patchxr.io/block-thumbnails/help_button.png)

## Description

A help toggle button. Pressing it switches the state and emits 1 (on) or 0 (off).

Useful for activating help texts or ghost recording tutorials. The latched state is preserved across saves.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set State | Jolt Input | Sets the state of the button with 0 (off) and 1 (on). |
| Highlight | Jolt Input | Controls the brightness of the button graphics from -1 (black) to 4 (white). |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| State Out | Jolt Output | Emits 0 or 1 depending on the button state. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Button | Button | Press to toggle between on (1) and off (0). |

## Related Blocks

- [play_button](/blocks/interfaces/play_button)
- [back_button](/blocks/interfaces/back_button)
- [reset_button](/blocks/interfaces/reset_button)
- [skip_button](/blocks/interfaces/skip_button)
- [toggle_new](/blocks/interfaces/toggle_new)

---