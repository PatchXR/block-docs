# Data Array

**Category**: 🧠 Logic

![data_array thumbnail](https://portal.patchxr.io/block-thumbnails/data_array.png)

## Description

Stores values at integer keys and recalls them by index. Useful for presets, sequencers, scores, or any kind of indexed lookup table.

Writing: send a jolt with the target index to 'Write index' to choose the slot, then send the value to 'value'. Reading: send a jolt with the desired index to 'Read index'; the stored value (or 0 if nothing was written there) is emitted on the 'value' output. Stored data is saved with the world so presets persist across sessions.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Read index | Jolt Input | Send a jolt with the index to read. The stored value at that index is emitted on the 'value' output (or 0 if empty). |
| Write index | Jolt Input | Selects which slot the next value sent to 'value' will be written to. |
| Write value | Jolt Input | Writes this jolt value into the slot last set by 'Write index'. Overwrites any existing value at that index. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Read value | Jolt Output | Emits the stored value each time 'Read index' is fired. Emits 0 if no value has been written at that index. |

## Related Blocks

- [get](/blocks/logic/get)
- [constant](/blocks/logic/constant)
- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)
- [cyclecounter](/blocks/logic/cyclecounter)

---