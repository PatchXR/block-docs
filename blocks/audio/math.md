# Math Stream

**Category**: 🔊 Audio

![math thumbnail](https://portal.patchxr.io/block-thumbnails/math.png)

## Description

Performs mathematical operations on two stream inputs at audio rate. Operations: add, subtract, multiply, divide, power, logarithm, min, max, modulo.

Stream-based mathematical processor that applies the selected operation to two input streams in real-time. Use the operation selector dial to switch between different math functions.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input A | Stream Input | First operand for the math operation. |
| Input B | Stream Input | Second operand for the math operation. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Stream Output | Result of the selected math operation. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Operation Selector | Selector | Select the math operation to perform. 0: +, 1: -, 2: *, 3: /, 4: aᵇ, 5: log, 8: min, 9: max, 10: mod |
| Operation Selector | Selector | Select the math operation to perform. 0: +, 1: -, 2: *, 3: /, 4: aᵇ, 5: log, 8: min, 9: max, 10: mod |

## Related Blocks

- [clamp](/blocks/audio/clamp)
- [operation](/blocks/logic/operation)
- [function_stream](/blocks/audio/function_stream)
- [map](/blocks/audio/map)

---