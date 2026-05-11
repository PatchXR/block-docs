# Sunlight

**Category**: 🎨 Visual

![sunlight thumbnail](https://portal.patchxr.io/block-thumbnails/sunlight.png)

## Description

Overrides the world's directional sunlight color and orientation. Only one sun light can be active in a world at a time.

Place and rotate this block to set the direction of the world's sunlight (it points along the block's forward axis). HSV streams control the color of the sun and the global directional light. Useful for setting the time-of-day mood, creating reactive day/night cycles, or matching a venue's atmosphere.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Hue | Stream Input | Sun light hue (0 to 1) — picks a color around the color wheel. |
| Saturation | Stream Input | Sun light saturation (0 to 1) — 0 is white, 1 is fully saturated color. |
| Value | Stream Input | Sun light brightness/intensity (0 to 1). |

## Related Blocks

- [lightbulb](/blocks/visual/lightbulb)
- [magic_spotlight](/blocks/visual/magic_spotlight)
- [hsvtorgb](/blocks/visual/hsvtorgb)
- [block_set_color](/blocks/visual/block_set_color)

---