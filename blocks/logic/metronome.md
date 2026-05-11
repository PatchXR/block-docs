# Metronome

**Category**: 🧠 Logic

![metronome thumbnail](https://portal.patchxr.io/block-thumbnails/metronome.png)

## Description

Emits regular jolts at the specified frequency. Use it to drive rhythms, sequencers, or any time-based behavior.

Each tick outputs a jolt with value 1. Connect a stream to the Frequency input to vary the tempo dynamically, or send a jolt to the Set Phase input to reset/realign the beat.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Frequency | Stream Input | Number of ticks per second (in Hertz). |
| Set Phase | Jolt Input | Resets/aligns the metronome's phase. The jolt value is used as the new phase position. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Emitter | Jolt Output | Emits a jolt of value 1 on every tick. |

## Related Blocks

- [clock](/blocks/audio/clock)
- [rhythm](/blocks/audio/rhythm)
- [cyclecounter](/blocks/logic/cyclecounter)
- [delay_jolt_2](/blocks/logic/delay_jolt_2)
- [gate](/blocks/logic/gate)

---