# Ghost Looper

**Category**: 👨‍👩‍👧‍👦 Players

![ghost_looper thumbnail](https://portal.patchxr.io/block-thumbnails/ghost_looper.png)

## Description

Records yourself and plays it back as a ghost avatar that repeats your movements and interactions on instruments.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Trigger Recording / Playback | Jolt Input | Play / Record the ghost sequence. |
| Offset Time | Jolt Input | Offsets the ghost sequence playback by the given number of beats. |
| Pause On/Off | Jolt Input | Send 0 to pause and hide the ghost, 1 to continue playing. |
| Recording duration | Jolt Input | Length of the recording in bars (4 beats per bar). |
| Record Voice on/off | Jolt Input | Send >=0.5 to enable voice recording, <0.5 to disable. |
| Loop on/off | Jolt Input | Send >=0.5 to enable looping, <0.5 to play once. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Ghost loop ended | Jolt Output | Fires when the ghost loop reaches the end. |
| Is Recording | Jolt Output | 0  - Recording just started x  - Time of recording -1 - Recording Cancelled |
| State | Jolt Output | 0 Empty - 1 Standby - 2 Recording - 3 FinishingRecording - 4 Playback |
| Progress | Jolt Output | Progress time of the playback in beats. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Record/Play Button | Button | Hit the button once, get in position, then press "A" button on your controller to actually start the recording. When a ghost is recorded, hit this button to play/pause the recording. |
| Record Voice | Toggle Button | Also record voice from the microphone during recording. |
| Loop on/off | Toggle Button | Makes the recording loop when finished. |
| Clear | Toggle Button | Delete the ghost recording. |
| Cancel | Toggle Button | Abort recording. |
| Rewind | Toggle Button | Rewind recording to the beginning. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Hide when not playing | checkbox | When enabled, the ghost avatar is hidden whenever it's not actively playing back. |
| Solo group | integer | Assigns this looper to a solo group. Loopers in the same group mute each other so only one plays at a time. 0 disables grouping. |
| Don't process hover | checkbox | When enabled, the ghost's controllers don't fire hover events on blocks they pass over. |
| Don't process hit | checkbox | When enabled, the ghost's controllers don't trigger hit events on blocks they collide with. |
| Hide Controllers | checkbox | Hides the ghost's controller models during playback. |
| Ghost Type | dropdown | What gets recorded and played back. Default records movement + audio; the other options let you isolate ghost visuals, audio, and block interactions independently. |
| Reset to Record Position | button | Snaps the ghost back to the position it was in when recording started. |
| Load Ghost's Appearence on me | button | Applies the ghost's avatar appearance to your own avatar. |
| Apply my Appearence on Ghost | button | Applies your current avatar appearance to the recorded ghost. |

## Related Blocks

- [microphone](/blocks/audio/microphone)
- [bubble_recorder](/blocks/audio/bubble_recorder)
- [players](/blocks/players/players)
- [anchor](/blocks/players/anchor)

---