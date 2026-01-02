# bubble

**Category**: 🔊 Audio

![bubble thumbnail](https://portal.patchxr.io/block-thumbnails/bubble.png)

## Description

Bubble can be used to play an audio sample.

## Inputs, Outputs and Parts

**Bubble** *(interactive)*: Grab with two hands and pull to open.

**Bubble** *(interactive)*: Hit to start playback. Touch to stop.

**Play** *(jolt input)*: Send a jolt to start playback.

**Set begin time** *(jolt input)*: Set the point where playback should start (in seconds).

**Set end time** *(jolt input)*: Set the point where playback should stop (in seconds).

**Begin time** *(jolt output)*: Emits the sample start position (in seconds) when start time changes, and on playback start.

**End time** *(jolt output)*: Emits the end point (in seconds) when end time changes, and on playback start.

**Playback done** *(jolt output)*: Emits a jolt when playback stops. Connect to the 'Play' input to enable looping.

**Playback cursor** *(interactive)*: Playback cursor. Grab to scrub through the sample.

**Begin time** *(interactive)*: Begin time indicator. Grab to move.

**End time** *(interactive)*: End time indicator. Grab to move.

**Transpose** *(stream input)*: Transposes the sample up or down by the set number of semitones.

**Gain** *(stream input)*: Controls how loud the sample is.

**Stop** *(jolt input)*: Send a jolt to stop playback.

## Related Blocks

- [bubble_player](/blocks/bubble_player)
- [bubble_recorder](/blocks/bubble_recorder)

---

*Last updated: 2026-01-02 06:02*