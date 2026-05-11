# Big_Slider_Stream

**Category**: 🎚️ Interfaces

![slider thumbnail](https://portal.patchxr.io/block-thumbnails/slider.png)

## Description

A large slider that outputs a stream value between 0 and 1 based on the puck's position. The length can also be adjusted by dragging the end handle.

Click and drag the puck along the track to set a value between 0 and 1, which is continuously sent through the stream output. The slider's length can be customized by dragging the end handle. A jolt input is provided to set the position from elsewhere.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set | Jolt Input | Receives a jolt to set the slider's position from 0 to 1. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Stream Out | Stream Output | Continuously outputs the slider's position as a value between 0 and 1. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Puck | Draggable part | Click and drag the puck to change the slider's value from 0 to 1. |
| PULL Extend | Draggable part | Click and drag to change the length of the slider track. |

## Related Blocks

- [custom_slider](/blocks/interfaces/custom_slider)
- [slider_new](/blocks/interfaces/slider_new)
- [slider_jolt](/blocks/interfaces/slider_jolt)
- [sliderboard](/blocks/logic/sliderboard)
- [knob_new](/blocks/interfaces/knob_new)

---