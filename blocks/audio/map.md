# Map Stream

**Category**: 🔊 Audio

![map thumbnail](https://portal.patchxr.io/block-thumbnails/map.png)

## Description

Linearly remaps a stream value from an input range to an output range.

Continuously rescales the input stream from [Input range min, Input range max] to [Output range min, Output range max]. For example, can be used to scale a slider's 0-1 output to a 1-1000 range. Values outside the input range are mapped proportionally (not clamped) — pair with a clamp block if you need bounded output.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Stream Input | Stream value to remap. |
| Input range min | Stream Input | Lower bound of the input range. |
| Input range max | Stream Input | Upper bound of the input range. |
| Output range min | Stream Input | Lower bound of the output range. |
| Output range max | Stream Input | Upper bound of the output range. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Stream Output | Remapped stream value. |

## Related Blocks

- [clamp](/blocks/audio/clamp)
- [math](/blocks/audio/math)
- [map_jolt](/blocks/logic/map_jolt)

---