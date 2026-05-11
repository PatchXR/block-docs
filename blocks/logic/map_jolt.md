# Map Jolt

**Category**: 🧠 Logic

![map_jolt thumbnail](https://portal.patchxr.io/block-thumbnails/map_jolt.png)

## Description

Linearly remaps a jolt value from an input range to an output range. Emits the result as a jolt.

Each incoming jolt is rescaled from [Input range min, Input range max] to [Output range min, Output range max] and emitted on the output. For example, can be used to scale a 0-1 input to a 1-1000 range. Values outside the input range are mapped proportionally (not clamped).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input range min | Stream Input | Lower bound of the input range. |
| Input range max | Stream Input | Upper bound of the input range. |
| Output range min | Stream Input | Lower bound of the output range. |
| Output range max | Stream Input | Upper bound of the output range. |
| Input | Jolt Input | Jolt value to remap. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the remapped jolt value. |

## Related Blocks

- [map](/blocks/audio/map)
- [clamp](/blocks/audio/clamp)
- [operation](/blocks/logic/operation)

---