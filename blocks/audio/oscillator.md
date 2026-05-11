# Oscillator

**Category**: 🔊 Audio

![oscillator thumbnail](https://portal.patchxr.io/block-thumbnails/oscillator.png)

## Description

Audio oscillator with four waveform modes: sine, square, triangle and sawtooth. Frequency is set in Hz (cycles per second).

Fundamental sound source for subtractive synthesis. Pick the waveform with the Wave Type selector (or set it via the Wave type jolt input). Modulate the frequency with a stream to create vibrato, pitch sweeps or melodies, and use Phase offset / Reset phase for phase-aligned effects like supersaws or sync.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Reset phase | Jolt Input | On jolt, resets the oscillator's phase to the jolt value (0 to 1 covers one full cycle). |
| Wave type | Jolt Input | Sets the waveform of the oscillator. Values: 0 = sine, 1 = square, 2 = triangle, 3 = sawtooth. |
| Frequency (Hz) | Stream Input | Sets the frequency of the oscillator (in Hertz). |
| Phase offset | Stream Input | Shifts the phase of the oscillator output (0 to 1 covers one full cycle). |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Signal output | Stream Output | Oscillator audio output. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Waveform | interactive | The current waveform of the oscillator. Jolt values map to: 0 = sine, 1 = square, 2 = triangle, 3 = sawtooth. |
| Wave Type | Selector | Pick the waveform: sine, square, triangle, or sawtooth. |

## Related Blocks

- [noise](/blocks/audio/noise)
- [filter](/blocks/audio/filter)
- [envelope](/blocks/audio/envelope)
- [reverb](/blocks/audio/reverb)
- [delay](/blocks/audio/delay)
- [string](/blocks/audio/string)
- [wavefolder](/blocks/audio/wavefolder)

---