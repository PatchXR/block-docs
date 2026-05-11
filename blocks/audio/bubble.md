# Bubble

**Category**: 🔊 Audio

## Description

Plays an audio sample. Hit to start playback, touch to stop. Wire inputs for precise playback automation.

## Related Wiki Pages

[samples](/patching/samples)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Play | Jolt Input | Send a jolt to start playback. |
| Set begin time | Jolt Input | Set the point where playback should start (in seconds). |
| Set end time | Jolt Input | Set the point where playback should stop (in seconds). |
| MIDI Note | Stream Input | Pitch in MIDI note number. Note 60 (C4) plays at original pitch. Used by Bubble Player when connected. |
| Gain | Stream Input | Controls how loud the sample is. |
| Stop | Jolt Input | Send a jolt to stop playback. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Begin time | Jolt Output | Emits the sample start position (in seconds) when start time changes, and on playback start. |
| End time | Jolt Output | Emits the end point (in seconds) when end time changes, and on playback start. |
| Playback done | Jolt Output | Emits a jolt when playback stops. Connect to the 'Play' input to enable looping. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Bubble | interactive | Grab with two hands and pull to open. |
| Bubble | interactive | Hit to start playback. Touch to stop. |
| Playback cursor | Interactible | Playback cursor. Grab to scrub through the sample. |
| Begin time | Interactible | Begin time indicator. Grab to move. |
| End time | Interactible | End time indicator. Grab to move. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Quantize | checkbox | Snaps the sample start and end points to beat-aligned positions. |
| Remove clicks | checkbox | Applies a short fade at the sample boundaries to reduce clicks and pops. |

## Related Blocks

- [bubble_player](/blocks/audio/bubble_player)
- [bubble_recorder](/blocks/audio/bubble_recorder)
- [booper](/blocks/controllers/booper)

---