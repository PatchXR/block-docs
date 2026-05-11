# Button Play

**Category**: 🎚️ Interfaces

![play_button thumbnail](https://portal.patchxr.io/block-thumbnails/play_button.png)

## Description

A play/pause toggle button. Pressing it switches the state and emits 1 when switching to play or 0 when switching to pause.

Useful for musical playback control UI. Wire its output to a Metronome's start/stop, an envelope trigger, or any other gate.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set State | Jolt Input | Sets the state of the button with 0 (paused) and 1 (playing). |
| Highlight | Jolt Input | Controls the brightness of the button graphics from -1 (black) to 4 (white). |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| State Out | Jolt Output | Emits 0 or 1 depending on the play state. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Button | Button | Press to toggle between play (1) and pause (0). |

## Related Blocks

- [back_button](/blocks/interfaces/back_button)
- [reset_button](/blocks/interfaces/reset_button)
- [skip_button](/blocks/interfaces/skip_button)
- [help_button](/blocks/interfaces/help_button)
- [toggle_new](/blocks/interfaces/toggle_new)
- [metronome](/blocks/logic/metronome)

---