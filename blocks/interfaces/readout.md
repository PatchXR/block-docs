# Number Readout

**Category**: 🎚️ Interfaces

![readout thumbnail](https://portal.patchxr.io/block-thumbnails/readout.png)

## Description

Displays the number sent into the Stream/Jolt input as text. Used for building interfaces, debugging, and learning.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Stream Input | Send a stream or jolt to display its value. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Display | Text Display | Shows the number set via the stream input. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Decimals | slider | Number of decimal places to display (0 to 4). |
| Display midi note name | checkbox | When enabled, the incoming number is interpreted as a MIDI note number and displayed as a note name (e.g. "C4") instead of a number. |
| Background | checkbox | Show or hide the dark transparent background behind the text. |
| Custom font size | slider | Adjusts the text size on the display. |

## Related Blocks

- [number](/blocks/interfaces/number)
- [knob_new](/blocks/interfaces/knob_new)
- [value](/blocks/interfaces/value)
- [stream_capture](/blocks/audio/stream_capture)

---