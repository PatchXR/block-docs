# Button

**Category**: 🎚️ Interfaces

![button thumbnail](https://portal.patchxr.io/block-thumbnails/button.png)

## Description

Pushing the button will emit a number from the Jolt output, number is set by the Stream input.

Buttons are one of the basic blocks used to trigger stuff in your world. You can e.g. wire the output of a button to the 'play' input of a sample to trigger playback of that sample.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set Value | Stream Input | Sets the number value that the output will emit. |
| Trigger | Jolt Input | Triggers the push of the button and emits its set value. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Jolt Out | Jolt Output | Emits the set value when button is pushed.  Click & pull to generate a new Jolt wire.  |

### Others

| Name | Type | Description |
|------|------|-------------|
| Button | Button | Press to fire the jolt output with the currently set value. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Multiplayer Press | checkbox | When enabled, presses by any remote player fire the output for everyone. When disabled, only the local player's press triggers the output (useful when each player should get their own response, e.g. teleport). |

## Related Blocks

- [value](/blocks/interfaces/value)
- [slider](/blocks/interfaces/slider)
- [knob_new](/blocks/interfaces/knob_new)
- [trigger](/blocks/interfaces/trigger)
- [toggle_new](/blocks/interfaces/toggle_new)

---