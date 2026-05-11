# Clamp

**Category**: 🔊 Audio

![clamp thumbnail](https://portal.patchxr.io/block-thumbnails/clamp.png)

## Description

Clamps a stream value within a specified range. The output is the input clamped between the min and max values.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Stream Input | Value to be clamped within the range. |
| Range minimum | Stream Input | Minimum of the clamp range. Output will never go below this value. |
| Range maximum | Stream Input | Maximum of the clamp range. Output will never go above this value. |

## Related Blocks

- [map](/blocks/audio/map)
- [math](/blocks/audio/math)
- [function_stream](/blocks/audio/function_stream)
- [operation](/blocks/logic/operation)

---