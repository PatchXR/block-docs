# Speaker

**Category**: 🔊 Audio

![output thumbnail](https://portal.patchxr.io/block-thumbnails/output.png)

## Description

Sends an audio stream to the speakers/headset. Supports panning and 3D spatialization based on the speaker's world position relative to the player.

Plug any audio stream into the Input. 'Spatialness' (0-1) blends between 2D playback and full 3D spatialization. 'Drop Off' sets the distance (in meters) at which the sound fades out - larger values reach further. Every Speaker is a separate mixer channel; copying one creates a new channel.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Stream Input | Audio stream input. |
| Pan | Stream Input | Stereo balance, -1 (full left) to +1 (full right). Attenuated by Spatialness when 3D mode is on. |
| Spatialness | Jolt Input with Dial | Blends from 2D (0) to fully 3D-positioned audio (1). At 1 the listener hears the sound coming from the speaker's location in the world. |
| Drop Off | Jolt Input with Dial | Distance (meters) at which the audio fades out. Beyond this distance the speaker is inaudible. |

## Related Blocks

- [oscillator](/blocks/audio/oscillator)
- [reverb](/blocks/audio/reverb)
- [microphone](/blocks/audio/microphone)
- [stream_capture](/blocks/audio/stream_capture)
- [listener](/blocks/audio/listener)

---