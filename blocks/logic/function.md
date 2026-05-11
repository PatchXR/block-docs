# Function Jolt

**Category**: 🧠 Logic

![function thumbnail](https://portal.patchxr.io/block-thumbnails/function.png)

## Description

Applies a math function to incoming jolt values: sin, cos, tanh, floor, round, ceil, abs, 1-x, sign, and MIDI-to-frequency (m2f).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set Type Reciever | Jolt Input | Sets the function by index. 0: sin, 1: cos, 2: tanh, 3: floor, 4: abs, 5: 1-x, 6: sign, 7: round, 8: ceil, 9: m2f (MIDI to Hz). |
| Input | Jolt Input | Input value. Receiving a jolt here applies the selected function and fires the output. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the result of the selected function applied to the most recent Input value. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Operation | Selector | Click & drag the dial to choose between different functions: abs, round, sign, sin, cos, tanh, 1-x, floor, ceil, m2f. |

## Related Blocks

- [function_stream](/blocks/audio/function_stream)
- [operation](/blocks/logic/operation)
- [math](/blocks/audio/math)
- [constant](/blocks/logic/constant)

---