# Lightbulb

**Category**: 🎨 Visual

![lightbulb thumbnail](https://portal.patchxr.io/block-thumbnails/lightbulb.png)

## Description

Adds a colored light source to the scene, with HSV (Hue/Saturation/Value) inputs. Use the radial menu to switch between point and spotlight, and to tweak quality and spotlight angle.

A patchable light source. Modulate the Hue, Saturation, and Value streams to create reactive lighting (e.g. drive Value with an audio envelope for a beat-reactive bulb). Use the radial menu to change the light Quality (Default/Pixel) and toggle between Point and Spot modes; spotlight angle is editable in the radial menu and can be modulated via jolt input.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Hue | Stream Input | Light hue (0 to 1) — controls the color around the color wheel (red, green, blue, etc.). |
| Saturation | Stream Input | Light saturation (0 to 1) — 0 is white/grey, 1 is fully saturated color. |
| Value | Stream Input | Light brightness/intensity (0 to 1) — 0 is dark, 1 is fully lit. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Hide Inputs | checkbox | Hides the bulb's physical body (and HSV input arms) so only the cast light remains visible. |

## Related Blocks

- [sunlight](/blocks/visual/sunlight)
- [magic_spotlight](/blocks/visual/magic_spotlight)
- [hsvtorgb](/blocks/visual/hsvtorgb)
- [block_set_color](/blocks/visual/block_set_color)
- [set_material](/blocks/visual/set_material)

---