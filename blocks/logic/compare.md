# Compare

**Category**: 🧠 Logic

![compare thumbnail](https://portal.patchxr.io/block-thumbnails/compare.png)

## Description

Compares the incoming jolt value with a stream value and outputs the result of the comparison as a boolean (false - 0, true - 1).

Supports equality, inequality, greater/less than (inclusive variants), and bitwise AND/OR/XOR operations. The operation can be changed via the dial or set remotely via the Set Operation jolt input.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Compare with | Stream Input | Sets the value that will be compared with the incoming value from the jolt input (without triggering the output). |
| Set Operation | Jolt Input | 0: =, 1: !=, 2: >, 4: >=, 3: <, 5: <=, 6: &, 7: |, 8: ^ |
| Input | Jolt Input | Receives value which will be compared with value set in the stream input, triggers the comparison. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits boolean result (false - 0, true - 1) of jolt and stream values comparison on each received jolt. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Comparison operation | Selector | Sets the type of the comparison operation. |

## Related Blocks

- [if_else](/blocks/logic/if_else)
- [operation](/blocks/logic/operation)
- [gate](/blocks/logic/gate)

---