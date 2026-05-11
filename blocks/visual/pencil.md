# Pencil

**Category**: 🎨 Visual

![pencil thumbnail](https://portal.patchxr.io/block-thumbnails/pencil.png)

## Description

Draw 3D lines in space with adjustable colour, thickness and palette. Joystick up/down changes thickness, left/right cycles through the colour palette.

Grab the pencil and press the trigger to draw. While grabbed, joystick vertical adjusts line thickness and joystick horizontal steps through the world's colour palette. Use the colour picker dial on the side for free-form HSV colour. The Manual Draw jolt input lets you trigger drawing programmatically (e.g. from a metronome) without grabbing the pencil.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Manual Draw | Jolt Input | Trigger drawing programmatically. Non-zero values draw a stroke at the pencil tip; the value also scales the stroke thickness. |
| Thickness | Jolt Input with Dial | Thickness of the drawn line. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Drawing | Sub Part | The drawn strokes left in space by the pencil. |
| Colour Picker | Sub Part | HSV colour picker for the pencil ink. Use the diamond to pick saturation/value, and the ring for hue. |

## Related Blocks

- [trail_pencil](/blocks/visual/trail_pencil)
- [procedural_line](/blocks/visual/procedural_line)
- [material_brush](/blocks/visual/material_brush)
- [color_brush](/blocks/visual/color_brush)
- [vfx](/blocks/visual/vfx)

---