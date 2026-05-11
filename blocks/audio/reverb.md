# Reverb

**Category**: 🔊 Audio

![reverb thumbnail](https://portal.patchxr.io/block-thumbnails/reverb.png)

## Description

Adds spaciousness and depth to a stream with three selectable reverb algorithms: FDN (clean digital hall), Tank (vintage spring), and Freeverb.

Use Decay Time to control how long the reverb tail lasts and Absorption to roll off the highs over time (higher values = darker tail). Mix balances dry signal vs. wet reverb. Switch algorithms with the dial on top - the swap happens on the audio thread without crackles.

## Related Wiki Pages

[audio-filters](/patching/audio-filters)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Stream Input | The audio stream to apply reverb to. |
| Decay time | Stream Input | Controls how long it takes for the sound to die out (in seconds) |
| Absorption | Stream Input | How quickly high frequencies are damped in the tail (0-1). Higher = darker reverb. |
| Mix | Stream Input | Balance between dry signal (0) and wet reverb (1). |
| Knob | Jolt Input with Dial |  |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Stream Output | Wet/dry mixed reverb output. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Type Dial | Selector | Switches between three reverb algorithms: FDN (clean digital hall), Tank (vintage spring), Freeverb (classic Schroeder-style). |

## Related Blocks

- [delay](/blocks/audio/delay)
- [filter](/blocks/audio/filter)
- [statevariable](/blocks/audio/statevariable)
- [allpass2](/blocks/audio/allpass2)
- [output](/blocks/audio/output)

---