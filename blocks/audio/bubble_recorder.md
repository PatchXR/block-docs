# Bubble Recorder

**Category**: 🔊 Audio

![bubble_recorder thumbnail](https://portal.patchxr.io/block-thumbnails/bubble_recorder.png)

## Description

Tool for recording new audio into a sample bubble.

## Inputs, Outputs and Parts

**Receptacle** *(interactive)*: Place a bubble here to connect it to the player.

**Record** *(jolt input)*: Send a jolt to start recording (from the begin point).

**Stop**: Send a jolt to stop recording.

**Set begin time** *(jolt input)*: Sets the point to start recording from (in seconds).

**Set end time** *(jolt input)*: Sets the point that will trigger 'Recording end' to fire (in seconds). Recording will always continue until a jolt is received through 'Stop'. To stop at this point make a connection from 'Recording end' to 'Stop'.

**Recording end** *(jolt output)*: Emits a jolt when the recording passes the end point.

**Audio input** *(stream input)*: Input for the audio to record.

**Record cursor** *(interactive)*: Shows what part of the sample is being recorded to.

**Begin time** *(interactive)*: Shows where recording will begin. Grab to move.

**End time** *(interactive)*: Shows where a jolt will be emitted through 'Recording end'. Grab to move.

**Bubble placed** *(jolt output)*: Emits a jolt with value 1 when a bubble is placed and value 0 when a bubble is removed.

## Related Blocks

- [bubble](/blocks/audio/bubble)
- [bubble_player](/blocks/audio/bubble_player)

---

*Last updated: 2026-01-02 06:44*