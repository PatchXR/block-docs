# Slider Jolt

**Category**: 🎚️ Interfaces

![slider_jolt thumbnail](https://portal.patchxr.io/block-thumbnails/slider_jolt.png)

## Description

A linear slider with Jolt input and output. Drag the handle, use the joystick, or send a Jolt to set the value (default 0-1).

A resizable linear slider that by default sends out values between zero and one. The min, max and midpoint values can be changed via the inspector.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| input | Jolt Input | Send a jolt (normally between zero and one) to set the value of the slider. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| output | Jolt Output | Sends out the value of the slider. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Drag to change length. |
| Value | Draggable part | Drag to change the value of the slider. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Lock size | checkbox | When enabled, prevents the slider length from being changed by dragging. |
| Minimum | text_input | Sets the minimum output value (maps to the slider's start position). |
| Maximum | text_input | Sets the maximum output value (maps to the slider's end position). |
| Exponential | checkbox | When enabled, applies an exponential curve to the output, giving more precision at low values. |

## Related Blocks

- [slider_new](/blocks/interfaces/slider_new)
- [slider_3d_jolt](/blocks/controllers/slider_3d_jolt)
- [knob_block](/blocks/interfaces/knob_block)

---