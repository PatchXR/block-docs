# Button Back

**Category**: 🎚️ Interfaces

![back_button thumbnail](https://portal.patchxr.io/block-thumbnails/back_button.png)

## Description

A momentary 'back' button. Pressing it emits a 1 from the Jolt output.

Useful for musical playback control UI, e.g. wired to a Counter to step backwards through a sequence.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Highlight | Jolt Input | Controls the brightness of the button graphics from -1 (black) to 4 (white). |
| Trigger | Jolt Input | Triggers the push of the button and emits 1 from the Jolt output. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Jolt Out | Jolt Output | Emits 1 when button is pushed. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Button | Button | Press to emit a 1 from the Jolt output. |

## Related Blocks

- [help_button](/blocks/interfaces/help_button)
- [play_button](/blocks/interfaces/play_button)
- [reset_button](/blocks/interfaces/reset_button)
- [skip_button](/blocks/interfaces/skip_button)
- [button](/blocks/interfaces/button)

---