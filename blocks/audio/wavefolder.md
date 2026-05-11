# Wavefolder

**Category**: 🔊 Audio

![wavefolder thumbnail](https://portal.patchxr.io/block-thumbnails/wavefolder.png)

## Description

A waveshaper that folds any part of the input signal that exceeds the [-1, 1] range back inside, creating extra harmonics and gritty timbres. Drive the input above 1 to hear the effect.

Boost an oscillator or any audio signal with a Math Stream (multiply) before sending it here to push values out of [-1, 1] - the further you go, the more folds and harmonic content you add. Classic for west-coast / Buchla-style synthesis: clean sine waves quickly turn buzzy and aggressive when folded.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Signal input | Stream Input | Audio signal to fold. Values above 1 or below -1 are mirrored back into the [-1, 1] range, adding harmonics. |

## Related Blocks

- [oscillator](/blocks/audio/oscillator)
- [math](/blocks/audio/math)
- [clamp](/blocks/audio/clamp)
- [filter](/blocks/audio/filter)
- [statevariable](/blocks/audio/statevariable)
- [wavefolder](/blocks/audio/wavefolder)

---