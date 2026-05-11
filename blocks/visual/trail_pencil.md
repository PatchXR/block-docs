# Trail Pencil

**Category**: 🎨 Visual

## Description

Pencil that leaves a glowing trail behind it as it moves. Width, lifetime and HSV colour are all patchable.

Grab and press the trigger to emit a trail. The trail fades after the configured lifetime. Unlike the regular Pencil, every parameter (width, lifetime, hue, saturation, brightness) is exposed as a Jolt Input with Dial, so the trail can be animated from other blocks.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Width | Jolt Input with Dial | Thickness of the emitted trail. |
| Trail Life Time | Jolt Input with Dial | How long (in seconds) each segment of the trail stays visible before fading out. |
| Hue | Jolt Input with Dial | Hue component of the trail colour (0-1, wraps around). |
| Saturation | Jolt Input with Dial | Colour saturation of the trail (0-1). |
| Brightness | Jolt Input with Dial | HSV brightness/value of the trail. Values above 1 push the colour into HDR for a glowy look. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Hide Pencil | checkbox | Hides the pencil body and colour picker mesh, leaving only the trail visible. Useful when driving the pencil via patches. |

## Related Blocks

- [pencil](/blocks/visual/pencil)
- [procedural_line](/blocks/visual/procedural_line)
- [vfx](/blocks/visual/vfx)
- [particles_sprite](/blocks/visual/particles_sprite)
- [hsvtorgb](/blocks/visual/hsvtorgb)

---