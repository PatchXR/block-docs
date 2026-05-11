# Allpass2

**Category**: 🔊 Audio

![allpass2 thumbnail](https://portal.patchxr.io/block-thumbnails/allpass2.png)

## Description

Second-order allpass filter. Passes the input signal through unchanged in amplitude but shifts its phase around a break frequency — the building block of phaser effects.

Chain several Allpass2 blocks and mix the result with the dry signal to build a classic phaser. The Frequency input sets the notch / break frequency, and the Radius controls how steep / resonant the phase shift is (typical values are slightly below 1).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Signal input | Stream Input | The input signal. |
| Frequency | Stream Input | Break frequency (in Hz) around which the phase shift is applied. |
| Radius | Stream Input | Pole radius — controls the steepness / resonance of the phase shift. Typical values are between 0 and 1. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Signal output | Stream Output | Phase-shifted signal. |

## Related Blocks

- lowpass (link not available)
- highpass (link not available)
- onepole (link not available)
- ladder (link not available)
- [statevariable](/blocks/audio/statevariable)

---