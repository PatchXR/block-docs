# Math Jolt

**Category**: 🧠 Logic

![operation thumbnail](https://portal.patchxr.io/block-thumbnails/operation.png)

## Description

Performs arithmetic on jolt events. Operations: add, subtract, multiply, divide, power, logarithm, minimum, maximum, modulo.

The block performs `a op b`, where 'a' is the value received on the Input A jolt input (which also triggers the output) and 'b' is the current value of the Input B stream input. Use the Swap Inputs inspector option to invert the operation (e.g. switch from b-a to a-b).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input B | Stream Input | Operand B, read from the stream when Input A triggers. |
| Input A | Jolt Input | Operand A. Receiving a jolt here applies the operation and fires the output. |
| Arithmetic Operation | Jolt Input | Sets the operation by index. 0: >, 1: get, 2: +, 3: a-b, 4: b-a, 5: *, 6: a/b, 7: b/a, 8: aᵇ, 9: bᵃ, 10: logᵦa, 11: logₐb, 12: a mod b, 13: b mod a, 14: min, 15: max. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the result of the selected operation each time Input A receives a jolt. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Arithmetic Operation | Selector | Click & drag the dial to choose between different operations. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Swap Inputs | checkbox | For non-commutative operations (subtract, divide, power, log, modulo), swaps the operands so the operation becomes 'b op a' instead of 'a op b'. The selected operation in the dial flips between its forward and reverse variants. |

## Related Blocks

- [math](/blocks/audio/math)
- [function](/blocks/logic/function)
- [function_stream](/blocks/audio/function_stream)
- [constant](/blocks/logic/constant)
- [get](/blocks/logic/get)
- [compare](/blocks/logic/compare)

---