# Particles

**Category**: 🎨 Visual

![particles_sprite thumbnail](https://portal.patchxr.io/block-thumbnails/particles_sprite.png)

## Description

Customizable particle system with sprite support. Control emission, movement, colors, and use custom images as particle sprites.

Advanced particle generator with comprehensive control over emission frequency, particle size, speed, lifetime, and visual properties. Features HSV color controls, noise-based movement, emission radius/direction settings, and the ability to use custom images as particle sprites. Includes real-time vs. future-only parameter application modes.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Emission Frequency | Jolt Input with Dial | Rate of particle generation (particles per second) |
| Emission Radius | Jolt Input with Dial | Size of the emission area (larger = more spread out spawn) |
| Emission Random Direction | Jolt Input with Dial | Amount of randomness in particle launch direction |
| Color Hue | Jolt Input with Dial | Particle color hue (0-1 range) |
| Color Saturation | Jolt Input with Dial | Particle color saturation (0-1 range) |
| Color Value | Jolt Input with Dial | Particle color brightness/value (0-1 range) |
| Particle Speed | Jolt Input with Dial | Initial velocity of emitted particles |
| Particle Size | Jolt Input with Dial | Scale of individual particles |
| Particle Lifetime | Jolt Input with Dial | Duration particles exist before disappearing (seconds) |
| Noise Intensity | Jolt Input with Dial | Strength of turbulent movement applied to particles |
| Noise Frequency | Jolt Input with Dial | Speed of noise pattern changes affecting particle movement |
| Sprite Source | Tag Input | Connect image block to use custom texture as particle sprite |
| Emission Burst | Jolt Input | Spawn particles each time it receives a jolt. (Sending 3 will spawn 3 particles) |
| Particle Has Trail | Jolt Input | Makes particles to leave a trail behind them. |
| Speed X | Jolt Input | Constant velocity along the X axis applied to all particles over their lifetime. |
| Speed Y | Jolt Input | Constant velocity along the Y axis applied to all particles over their lifetime (e.g. positive for floating up). |
| Speed Z | Jolt Input | Constant velocity along the Z axis applied to all particles over their lifetime. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Size/Color affect current particles | Toggle | Should Size/Color changes affect all current particles (ON) or only future generated particles. (OFF) |
| Color picker | Interactible | Can connect a "Set Color" block to it. |
| Previous Sprite | Interactible | Explore the different image preset |
| Next Sprite | Interactible | Explore the different image preset |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Simulate World Space | checkbox | When enabled, particles stay in world space when the block is moved (they trail behind). When disabled, particles follow the block. |
| Collide with meshes | checkbox | When enabled, particles bounce off and stop against scene meshes. Costs more performance. |
| Render type | dropdown | Particle blending mode. Additive: bright/glowing overlap. Alpha Blend: standard transparency. |

## Related Blocks

- [image](/blocks/visual/image)
- [snapshot](/blocks/visual/snapshot)
- [hsvtorgb](/blocks/visual/hsvtorgb)

---