# Microphone

**Category**: 🔊 Audio

![microphone thumbnail](https://portal.patchxr.io/block-thumbnails/microphone.png)

## Description

Outputs the live microphone audio as a stream. Supports spatial mode (volume falls off with distance from the player) or 2D mode (constant volume).

Captures audio from the system microphone and exposes it as a stream output for routing into effects, samplers, or speakers. By default the mic is spatial: as the player moves away from the block, the output volume fades out, reaching silence at the configured range. The Radial Menu provides 'Switch to 2D' (constant volume regardless of distance) and a 'Range' control to set the spatial falloff distance.

## Related Wiki Pages

[samples](/patching/samples)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Audio Out | Stream Output | Microphone audio stream output. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Grab sphere VR | Sub Part | Handle used to grab and move the block in VR. |

## Related Blocks

- [mic](/blocks/controllers/mic)
- [output](/blocks/audio/output)
- [bubble_recorder](/blocks/audio/bubble_recorder)

---