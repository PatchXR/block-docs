# Button Reset

**Category**: 🎚️ Interfaces

![reset_button thumbnail](https://portal.patchxr.io/block-thumbnails/reset_button.png)

## Description

A momentary 'reset' button. Pressing it emits a 1 from the Jolt output.

Useful for musical playback control UI or as a reset signal wired to counters, sequencers, or any state-holding block.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Trigger | Jolt Input | Triggers the push of the button and emits 1 from the Jolt output. |
| Highlight | Jolt Input | Controls the brightness of the button graphics from -1 (black) to 4 (white). |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Jolt Out | Jolt Output | Emits 1 when button is pushed. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Button | Button | Press to emit a 1 from the Jolt output. |

## Related Blocks

- [back_button](/blocks/interfaces/back_button)
- [play_button](/blocks/interfaces/play_button)
- [skip_button](/blocks/interfaces/skip_button)
- [help_button](/blocks/interfaces/help_button)
- [button](/blocks/interfaces/button)

---