# HSV to RGB

**Category**: 🎨 Visual

## Description

Converts HSV color values to RGB. Input hue, saturation, value as streams and get red, green, blue streams out.

Color space conversion utility that transforms HSV (Hue, Saturation, Value) into RGB (Red, Green, Blue). Useful for color calculations and patching color pickers to blocks that expect RGB inputs. All values operate in the 0-1 range.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Hue Input | Stream Input | Hue stream input (0-1). Represents the position on the color wheel. |
| Saturation Input | Stream Input | Saturation stream input (0-1). Controls the color intensity (0 = grayscale, 1 = pure color). |
| Value Input | Stream Input | Value/brightness stream input (0-1). Controls how light or dark the color is. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Red Output | Stream Output | Stream output for the red component of the converted RGB color (0-1). |
| Green Output | Stream Output | Stream output for the green component of the converted RGB color (0-1). |
| Blue Output | Stream Output | Stream output for the blue component of the converted RGB color (0-1). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Grab sphere VR | Sub Part | Handle used to grab and move the block in VR. |

## Related Blocks

- [block_set_color](/blocks/visual/block_set_color)
- [color_brush](/blocks/visual/color_brush)
- [set_material](/blocks/visual/set_material)

## Tags

To Refurbish

---