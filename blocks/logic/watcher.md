# Watcher

**Category**: 🧠 Logic

![watcher thumbnail](https://portal.patchxr.io/block-thumbnails/watcher.png)

## Description

Compares two stream values. Outputs a continuous 0/1 signal while the condition holds, and fires a jolt whenever the result transitions from false to true.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Signal input | Stream Input | Stream input value to compare with value from second inlet. |
| Compare with | Stream Input | Sets the value that will be compared with the incoming value from the signal input. |
| Set Operation | Jolt Input | Sets the comparison operator by index. 0: =, 1: !=, 2: >, 3: <, 4: >=, 5: <=, 6: &, 7: |, 8: ^ |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Fires a jolt each time the comparison result becomes true. |
| Output 0-1 | Stream Output | Outputs 1 continuously while the condition is true, 0 while false. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Operation | Selector | Choose compare operation. |

## Related Blocks

- [compare](/blocks/logic/compare)
- [stoe](/blocks/connectors/stoe)

---