# If Else

**Category**: 🧠 Logic

![if_else thumbnail](https://portal.patchxr.io/block-thumbnails/if_else.png)

## Description

Compares the incoming jolt value with a stream value and routes the jolt to one of two outputs depending on whether the condition is met.

Supports equality, inequality, greater/less than (inclusive variants), and bitwise AND/OR/XOR operations. The operation can be changed via the dial or set remotely via the Set Operation jolt input.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set Operation | Jolt Input | 0: =, 1: !=, 2: >, 4: >=, 3: <, 5: <=, 6: &, 7: |, 8: ^ |
| Input | Jolt Input | Receives value which will be compared with value set in the stream input, triggers the comparison. |
| Compare with | Stream Input | Sets the value that will be compared with the incoming value from the jolt input (without triggering the output). |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output if | Jolt Output | Emits received jolt value if the condition is met. |
| Output else | Jolt Output | Emits received jolt value if the condition is not met. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Comparison operation | Selector | Sets the type of the comparison operation. |

## Related Blocks

- [compare](/blocks/logic/compare)
- [gate](/blocks/logic/gate)
- [route](/blocks/logic/route)
- [bernoulli](/blocks/logic/bernoulli)

---