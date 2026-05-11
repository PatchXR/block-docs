# Spectrum Capture

**Category**: 🔊 Audio

![spectrum_capture thumbnail](https://portal.patchxr.io/block-thumbnails/spectrum_capture.png)

## Description

Performs FFT (frequency spectrum) analysis on an incoming audio stream. Use a 0-1 cursor on the Read input to scan through the frequency bins.

Drive the Read cursor with a clock from 0 to 1 (e.g. via Stream Capture's progress, or any ramp) - the Output emits the magnitude of each frequency bin in order, from low to high. Wire the Output into a Procedural Line's thickness or Y position to draw a live spectrum analyzer.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Stream Input | The signal you wish to analyze. |
| Read cursor | Stream Input | Expects a clock going 0→1. Maps to frequency bins from low (0) to high (1) on the Output. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Stream Output | Magnitude of the frequency bin at the current Read cursor position. |

## Related Blocks

- [stream_capture](/blocks/audio/stream_capture)
- [procedural_line](/blocks/visual/procedural_line)
- [filter_eq](/blocks/audio/filter_eq)
- [filter](/blocks/audio/filter)
- [oscillator](/blocks/audio/oscillator)

---