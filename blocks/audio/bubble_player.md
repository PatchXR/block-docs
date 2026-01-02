# Bubble Player

**Category**: 🔊 Audio

![bubble_player thumbnail](https://portal.patchxr.io/block-thumbnails/bubble_player.png)

## Description

Interface for connecting an audio sample bubble with the rest of your patch.

## Inputs, Outputs and Parts

**Receptacle** *(interactive)*: Place a bubble here to connect it to the player.

**Play** *(jolt input)*: Send a jolt to start playback.

**Stop** *(jolt input)*: Send a jolt to stop playback.

**Set begin time** *(jolt input)*: Set the point where playback should start (in seconds).

**Set end time** *(jolt input)*: Set the point where playback should stop (in seconds).

**Begin time** *(jolt output)*: Emits the sample start position (in seconds) when start time changes, and on playback start.

**End time** *(jolt output)*: Emits the end point (in seconds) when end time changes, and on playback start.

**Playback done** *(jolt output)*: Emits a jolt when the playback reaches the end point. Connect to the 'Play' input to enable looping.

**MIDI Note or Playback Speed** *(stream input)*: You can switch mode, from MIDI Note to Playback Speed, using the inspector.
- MIDI Note: input is midi semitones. Midi note 60 (C4) = original speed.
- Playback Speed: input will be the speed of the sample. 1x = original speed.

**Gain** *(stream input)*: Controls how loud the output audio is.

**Cursor** *(stream input)*: Directly controls the playback position of the audio (in seconds). Used in advanced patching by those who want complete control over the audio playback.

**Playback cursor** *(interactive)*: Shows what part of the audio is currently being played. Drag to scrub through the audio.

**Begin time** *(interactive)*: Begin time indicator. Grab to move.

**End time** *(interactive)*: End time indicator. Grab to move.

**Bubble placed** *(jolt output)*: Emits a jolt with value 1 when a bubble is placed and value 0 when a bubble is removed.

## Related Blocks

- [bubble](/blocks/audio/bubble)
- [bubble_recorder](/blocks/audio/bubble_recorder)

---

*Last updated: 2026-01-02 06:44*