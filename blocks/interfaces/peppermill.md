# Peppermill

**Category**: 🎚️ Interfaces

![peppermill thumbnail](https://portal.patchxr.io/block-thumbnails/peppermill.png)

## Description

A crank-style knob: grab the handle and rotate it around the central axis to change its value. The current value is exposed as a stream output and can also be set/read via the jolt input.

Tactile control well suited for unbounded, expressive parameters — like grinding pepper. Drag the handle in a circular motion to turn the dial; the output value increases or decreases with each rotation. Useful for momentary playback gestures, pitch-bend-style controls, or accumulating counters.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set Value | Jolt Input | Sets the current value of the peppermill to the incoming jolt's value. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Dial Body | Dial | Twist the body to change the current value. |
| Crank Handle | Draggable part | Grab and rotate this handle around the dial's axis to turn the peppermill. |
| Grab sphere VR | Sub Part | Grab area for moving the whole block. |

## Related Blocks

- [custom_knob](/blocks/interfaces/custom_knob)
- [custom_knob2](/blocks/interfaces/custom_knob2)
- [knob_new](/blocks/interfaces/knob_new)
- [knob_block](/blocks/interfaces/knob_block)
- [stream_input](/blocks/interfaces/stream_input)
- [slider_new](/blocks/interfaces/slider_new)

---