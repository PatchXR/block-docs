# Integrator

**Category**: 🔊 Audio

![integrator thumbnail](https://portal.patchxr.io/block-thumbnails/integrator.png)

## Description

A leaky integrator with separate rise and fall time constants. Smooths an incoming signal so that the level can only change by a limited amount per second.

Useful as a slew limiter, lag/portamento, or low-pass smoother for control signals. Combine with an absolute-value step (e.g. through a Math Stream) to build an envelope follower that tracks the loudness of an audio signal. The Set Value jolt jumps the internal state to a specific number — usually you also want to update the Signal input at the same time so it doesn't immediately drift back.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Signal input | Stream Input | The signal to integrate. |
| Rise control | Stream Input | Integration constant used while the signal is rising. Higher values track faster, lower values smooth more. |
| Fall control | Stream Input | Integration constant used while the signal is falling. Higher values track faster, lower values smooth more. |
| Set value | Jolt Input | Immediately sets the internal value of the integrator. Usually you also want to set the Signal input so the value doesn't drift back. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Signal output | Stream Output | Smoothed (integrated) signal. |

## Related Blocks

- [math](/blocks/audio/math)
- [function_stream](/blocks/audio/function_stream)
- [envelope](/blocks/audio/envelope)
- [clamp](/blocks/audio/clamp)
- [watcher](/blocks/logic/watcher)

---