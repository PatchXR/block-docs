# Slider 3d Jolt

**Category**: 🎮 Controllers

![slider_3d_jolt thumbnail](https://portal.patchxr.io/block-thumbnails/slider_3d_jolt.png)

## Description

A three-axis 3D slider with Jolt inputs and outputs for all three axes. Drag the ball or send a Jolt to set each axis value (0-1 range).

Has three resizable axes. Sends out a jolt per axis and has jolt inputs to set the value along each axis individually.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input X | Jolt Input | Send a jolt between zero and one to set the value along the X axis. |
| Input Y | Jolt Input | Send a jolt between zero and one to set the value along the Y axis. |
| Input Z | Jolt Input | Send a jolt between zero and one to set the value along the Z axis. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output X | Jolt Output | Sends out the value of the X axis. |
| Output Y | Jolt Output | Sends out the value of the Y axis. |
| Output Z | Jolt Output | Sends out the value of the Z axis. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Drag to resize |
| Value | Draggable part | Drag to change the output value |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Lock size | checkbox | When enabled, prevents all three axes from being resized by dragging. |

## Related Blocks

- [slider_3d](/blocks/controllers/slider_3d)
- [slider_jolt](/blocks/interfaces/slider_jolt)
- [slider_new](/blocks/interfaces/slider_new)

---