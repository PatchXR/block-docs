# Listener

**Category**: 🔊 Audio

![listener thumbnail](https://portal.patchxr.io/block-thumbnails/listener.png)

## Description

Taps into the world's master mix: listens to every Speaker (output) block, sums them into a single stream and exposes it as a stream output. Useful for sidechain, metering or recording the whole patch.

Connect the output to a Spectrum Capture or Stream Capture to visualise the master mix, to an Envelope/Integrator to drive sidechain ducking, or to a Reverb to add a global effect over everything that is currently playing through Speakers.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Signal output | Stream Output | Sum of every Speaker (output) block currently in the world. |

## Related Blocks

- [output](/blocks/audio/output)
- [microphone](/blocks/audio/microphone)
- [stream_capture](/blocks/audio/stream_capture)
- [spectrum_capture](/blocks/audio/spectrum_capture)
- [envelope](/blocks/audio/envelope)

---