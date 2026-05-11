# Slider 3d

**Category**: 🎮 Controllers

![slider_3d thumbnail](https://portal.patchxr.io/block-thumbnails/slider_3d.png)

## Description

A three-dimensional controller with a draggable ball. Drag the ball in 3D space to output its normalized X, Y, Z positions (0-1). Pull the sticks to extend each axis range.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Show/Hide Ball | Jolt Input | Shows the ball when the value is above 0.5, hides it when 0. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Extend X | Draggable part | Drag to resize the X axis range. |
| Extend Y | Draggable part | Drag to resize the Y axis range. |
| Extend Z | Draggable part | Drag to resize the Z axis range. |
| Ball | Draggable part | Drag to set the output values. The ball position is normalized 0-1 per axis. |
| Output X | Sub Part | Outputs the normalized X position of the ball (0-1). |
| Output Y | Sub Part | Outputs the normalized Y position of the ball (0-1). |
| Output Z | Sub Part | Outputs the normalized Z position of the ball (0-1). |

## Related Blocks

- [slider_3d_jolt](/blocks/controllers/slider_3d_jolt)

---