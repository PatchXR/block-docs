# Vooper

**Category**: 🎮 Controllers

![vooper thumbnail](https://portal.patchxr.io/block-thumbnails/vooper.png)

## Description

Variant of the Booper with an extra slider on its side. Hit the dome with the controller or marbles to emit hit speed, azimuth, elevation and pressure jolts. Catches sample bubbles to play one-shot samples through connected sample players.

Tag a Sample Player (or Recorder) on the RecPlay Selector to play / record audio. Bring an audio sample bubble close to swallow it: it will play through the connected sample player on each hit. The Vooper exposes a rich set of jolt outputs (hit velocity, azimuth, elevation, pressure, hover, etc.) describing each hit, plus an additional slider on the side that emits a continuous value, perfect for filter sweeps or modulation.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| RecPlay Selector | Tag Input | Tag a Sample Player or a Sample Recorder so the vooper plays/records the loaded sample on each hit. |
| Toggle color | Jolt Input | Sets the toggle color tint (>0.5 highlighted, otherwise off). |
| Eject bubble | Jolt Input | Send a jolt to eject the currently loaded sample bubble. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Hit velocity | Jolt Output | Emits the velocity at which the vooper was hit. |
| Size | Jolt Output | Emits the current size of the vooper when it is hit. |
| Hit elevation | Jolt Output | Emits the normalized vertical position (0 to 1) where the vooper was hit. |
| Hit azimuth | Jolt Output | Emits the normalized rotational position (0 to 1) around the vooper where it was hit. |
| Distance to base part | Jolt Output | Emits the normalized distance from the hit point to the closest base black part. |
| Pressure | Jolt Output | Emits how deep the controller is pressing into the vooper while held. |
| Hover count | Jolt Output | Emits the number of controllers currently touching the vooper. |
| Crossfade | Jolt Output | When two sample players are tagged, emits the crossfade between them based on the bubble approach. |
| Distance to dot part | Jolt Output | Emits the normalized distance from the hit point to the closest small dot part. |
| Slider value | Jolt Output | Emits the value of the side slider (0 to 1) when it is moved. |
| Bubble placed | Jolt Output | Emits 1 when a bubble is placed and 0 when removed. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Hit dome | Button | Hit this surface with the controller (or marbles) to emit hit, azimuth, elevation, pressure and color information. |
| Resize | Draggable part | Drag this handle to resize the vooper. |
| Slider | Draggable part | Drag this fader to send a continuous value through the slider output. |

## Related Blocks

- [booper](/blocks/controllers/booper)
- [blooper2](/blocks/controllers/blooper2)
- [blooper3](/blocks/controllers/blooper3)
- [bubble_player](/blocks/audio/bubble_player)
- [bubble](/blocks/audio/bubble)

---