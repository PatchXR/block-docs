# Particles

**Category**: 🎨 Visual

![particles_sprite thumbnail](https://portal.patchxr.io/block-thumbnails/particles_sprite.png)

## Description

Customizable particle system with sprite support. Control emission, movement, colors, and use custom images as particle sprites.

Advanced particle generator with comprehensive control over emission frequency, particle size, speed, lifetime, and visual properties. Features HSV color controls, noise-based movement, emission radius/direction settings, and the ability to use custom images as particle sprites. Includes real-time vs. future-only parameter application modes.

## Inputs, Outputs and Parts

**Emission Frequency**: Rate of particle generation (particles per second)

**Emission Radius**: Size of the emission area (larger = more spread out spawn)

**Emission Random Direction**: Amount of randomness in particle launch direction

**Color Hue**: Particle color hue (0-1 range)

**Color Saturation**: Particle color saturation (0-1 range)

**Color Value**: Particle color brightness/value (0-1 range)

**Particle Speed**: Initial velocity of emitted particles

**Particle Size**: Scale of individual particles

**Particle Lifetime**: Duration particles exist before disappearing (seconds)

**Noise Intensity**: Strength of turbulent movement applied to particles

**Noise Frequency**: Speed of noise pattern changes affecting particle movement

**Sprite Source**: Connect image block to use custom texture as particle sprite

**Size/Color affect current particles**: Should Size/Color changes affect all current particles (ON) or only future generated particles. (OFF)

## Related Blocks

- [image](/blocks/visual/image)
- [snapshot](/blocks/visual/snapshot)
- [hsvtorgb](/blocks/visual/hsvtorgb)

---