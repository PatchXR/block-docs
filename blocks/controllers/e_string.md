# Violin String

**Category**: 🎮 Controllers

![e_string thumbnail](https://portal.patchxr.io/block-thumbnails/e_string.png)

## Description

A virtual string that emits values when bowed, touched, or hit. Designed to be played with the Bow block but reacts to any object.

Wire the outputs into audio blocks (oscillator frequency, envelope amplitude, etc.) to synthesize string-like sounds. Pressing the bow into the string gives negative Y values, sliding the bow along it produces rubbing velocity, and player touches output a position along the string for note selection.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Contact point on the bow | Jolt Output | Position along the bow where it contacts the string (its X coordinate in the string's local space). |
| Distance with bow | Jolt Output | Perpendicular distance from the string to the bow. Negative values indicate the bow is pressing into the string (use as pressure / bow force). |
| Contact point on string | Jolt Output | Position along the string where the bow is touching it. Often used to drive the pitch of the synthesized note. |
| Bowing rubbing speed | Jolt Output | Velocity of the bow along its own axis while rubbing the string. Drives the intensity of the bowed sound. |
| Bow hit speed | Jolt Output | Approach velocity perpendicular to the string. Spikes when the bow (or any object) strikes the string; useful to trigger plucks or impacts. |
| Bow rubbing speed sideway | Jolt Output | Velocity of the bow sliding sideways along the string (perpendicular to its own length). |
| Touch note | Jolt Output | When players touch the string, it outputs the position of their touch along the string. |

### Others

| Name | Type | Description |
|------|------|-------------|
| String | Sub Part | The interactive string itself. Touch, pluck, or bow it to drive the outputs. |

## Related Blocks

- [bow](/blocks/controllers/bow)
- [string](/blocks/audio/string)
- [oscillator](/blocks/audio/oscillator)
- [envelope](/blocks/audio/envelope)

---