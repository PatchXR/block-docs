# Vfx

**Category**: 🎨 Visual

![vfx thumbnail](https://portal.patchxr.io/block-thumbnails/vfx.png)

## Description

Library of visual effects (plasma, beams, rings, flares, vortexes, etc.). Pick a preset from the inspector; tint it with the block's colour.

A single block that cycles between many built-in VFX presets. Use the inspector's preset selector to step through Plasma, Particle Big, Particle Narrow, Beam, Ring, Disk, Flare and Vortex variants. The block's colour drives the effect tint. Enable Face me to make the effect billboard toward the camera.

## Inputs, Outputs and Parts

### Others

| Name | Type | Description |
|------|------|-------------|
| vfx | Sub Part | The visual effect emitter. Recolour the block to tint the effect. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Plasma | select_button | Cycles through the built-in VFX presets (Plasma, Particle Big/Narrow, Beam, Ring, Disk, Flare, Vortex...). |
| Face me | checkbox | When enabled, the effect billboards toward the local camera instead of staying fixed in world space. |

## Related Blocks

- [particles_sprite](/blocks/visual/particles_sprite)
- [magic_spotlight](/blocks/visual/magic_spotlight)
- [pencil](/blocks/visual/pencil)
- [trail_pencil](/blocks/visual/trail_pencil)
- [shape](/blocks/visual/shape)

---