# Blooper

**Category**: 🎮 Controllers

![blooper3 thumbnail](https://portal.patchxr.io/block-thumbnails/blooper3.png)

## Description

Catches an audio sample bubble and plays it as a synced loop. Touch the rotor to scratch and beat-repeat, press the center to start/stop. The loop length is rounded to powers of two to stay in sync with the beat.

Bring an audio sample bubble close to the Blooper to feed it. Once swallowed, the sample is played in sync with the global tempo (the loop length is automatically rounded to the nearest power of two beats). Touch the central button to start/stop playback. Touch the rotor (around the edge) to scratch the sample or to enter beat-repeat mode: the further from the center, the longer the repeat. Marbles can also hit it to toggle playback or trigger beat repeats. Use the radial menu to eject the bubble.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Loop length | Jolt Input | Sets the loop length in beats. Value is rounded to the nearest power of two between 0.25 and 32. |
| Eject bubble | Jolt Input | Send a jolt to eject the currently loaded sample bubble. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Sample output | Stream Output | Audio output of the loaded sample. |
| Bubble placed | Jolt Output | Emits a jolt with value 1 when a bubble is placed and value 0 when removed. |
| Is playing | Jolt Output | Emits a jolt with value 1 when the blooper starts playing and value 0 when it stops. |
| Beat repeat | Jolt Output | Emits a jolt whenever a beat repeat happens. The value is the duration of the beat repeat in beats. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Break the beat | Interactible | Press the center to start/stop, touch the rotor to scratch or enter beat-repeat. Distance from center sets the repeat length. |

## Related Blocks

- [blooper2](/blocks/controllers/blooper2)
- [booper](/blocks/controllers/booper)
- [vooper](/blocks/controllers/vooper)
- [ghost_looper](/blocks/players/ghost_looper)
- [bubble_player](/blocks/audio/bubble_player)
- [bubble](/blocks/audio/bubble)

---