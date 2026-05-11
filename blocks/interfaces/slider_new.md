# Slider

**Category**: 🎚️ Interfaces

![slider_new thumbnail](https://portal.patchxr.io/block-thumbnails/slider_new.png)

## Description

Touch, click & drag, or use the joystick up/down, to send the position of the slider from the Jolt output (default 0 to 1).

Used for controlling parameters of other blocks and devices (i.e. volume).
Behavior and min/max values can be adjusted from the inspector.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set & Trigger | Jolt Input | Receives 0 to 1 to set the position of the slider and output that positions value. Can be used to map 0-1 to other value ranges.  To connect another block here, click & pull on any Jolt output to create a wire and drag it here. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Slider Out | Jolt Output | Outputs the current position of the slider when it is changed (default 0 to 1).  Click & pull to generate a new Jolt wire. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Slider | Interactive | Touch, click and drag, or use the joystick up/down to change the output value. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Minimum | text_input | Sets the minimum output value (maps to the slider's start position). |
| Maximum | text_input | Sets the maximum output value (maps to the slider's end position). |
| Exponential | checkbox | When enabled, applies an exponential curve to the output, giving more precision at low values. |
| Interaction Type | dropdown | Controls when the output fires: Trigger (on trigger press), Touch (on contact), None. |
| Value Change | dropdown | Jump: value jumps to the touched position. Drag: value only changes while actively dragging. |
| Colorize | dropdown | Selects which part of the slider receives the block's color. |
| Hide Body | checkbox | When enabled, hides the slider body, showing only the indicator. |

## Related Blocks

- [slider_jolt](/blocks/interfaces/slider_jolt)
- [knob_block](/blocks/interfaces/knob_block)
- [readout](/blocks/interfaces/readout)

---