# Get Variable

**Category**: ⚙️ System

![get_variable thumbnail](https://portal.patchxr.io/block-thumbnails/get_variable.png)

## Description

Read a named variable from a block. If the block has the variable, its value is sent to "Output". If it doesn't, a 0 is sent to the "Fail" output instead.

The variable name must match the one used by "Set Variable". If "Set Variable" was restricted to a Group/Device, this block must use the same Restrict input to be able to read the value.

When the Manual Trigger jolt is not connected, this block automatically re-emits the value whenever the variable on the connected block changes (or whenever the Input changes).

See the [Variable System](/wiki/variable-system) wiki page for more details.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Variable Name | Text Input | Name of the variable to read. Must match the name used by the corresponding "Set Variable". |
| Input | Tag Input | Block(s) we want to read the variable from. |
| Restrict (Optional) | Tag Input | Connect the same Group or Device used by "Set Variable" to read its locally-scoped variable. |
| Manual Trigger | Jolt Input | If connected: only read the variable when this jolt fires. If not connected: the block re-emits automatically whenever the variable's value or the Input changes. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Outputs the value of the variable on the connected block (only if the block actually has it set). |
| Fail | Jolt Output | Sends 0 when the connected block does not have this variable attached. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Add restriction input | checkbox | Reveals the "Restrict" tag input. Required to read variables that were set with a matching restriction (i.e. local to a Group or Device). |
| Use Device on Input | checkbox | When ticked and a block inside a Device is connected to the Input, the variable is read from the parent Device instead of the inner block. |
| Edit text from outside | checkbox | When this block is placed inside a Group/Device, its text input is normally only editable from inside the group. Tick this option to let players still click and type into it from outside the group. |

## Related Blocks

- [set_variable](/blocks/system/set_variable)
- [all_with_variable](/blocks/system/all_with_variable)
- [remove_variable](/blocks/system/remove_variable)
- [fetch_variable](/blocks/system/fetch_variable)
- [block_foreach](/blocks/system/block_foreach)

---