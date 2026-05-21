# Remove Variable

**Category**: ⚙️ System

![remove_variable thumbnail](https://portal.patchxr.io/block-thumbnails/remove_variable.png)

## Description

Detach a named variable from one or more blocks. Once removed, the block no longer appears in "All With Variable" and "Get Variable" will fall back to its Fail output.

Use this block to clean up tags when something stops being relevant (e.g. when an enemy dies, untag it from "Alive"). The Input is omitted when "Remove on all blocks" is enabled in the inspector, in which case the variable is wiped from every block that currently has it.

See the [Variable System](/wiki/variable-system) wiki page for more details.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Variable Name | Text Input | Name of the variable to remove. Must match the name used by the corresponding "Set Variable". |
| Input | Tag Input | Block(s) we want to remove the variable from. Hidden when "Remove on all blocks" is enabled in the inspector. |
| Manual Trigger | Jolt Input | If connected: only remove the variable when this jolt fires. If not connected: the block triggers automatically when Input or Variable Name changes (only when "Remove on all blocks" is off). |
| Restrict (Optional) | Tag Input | Connect the same Group or Device used by "Set Variable" to remove only the locally-scoped version of the variable. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Add restriction input | checkbox | Reveals the "Restrict" tag input. Required to remove variables that were set with a matching restriction (i.e. local to a Group or Device). |
| Use Device on Input | checkbox | When ticked and a block inside a Device is connected to the Input, the variable is removed from the parent Device instead of the inner block. |
| Remove on all blocks | checkbox | When ticked, the Input is hidden and triggering the block removes this variable from every block that currently has it. |
| Also remove all Local | checkbox | Only visible when "Remove on all blocks" is enabled. Also wipes every locally-scoped (restricted) version of this variable across all Groups and Devices. |
| Edit text from outside | checkbox | When this block is placed inside a Group/Device, its text input is normally only editable from inside the group. Tick this option to let players still click and type into it from outside the group. |
| Broadcast Multiplayer | checkbox | Synchronizes the variable removal to all other players in the multiplayer session via RPC. Important: Ensure this block is triggered by only one player, otherwise everyone will broadcast the removal to everyone else! |

## Related Blocks

- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)
- [all_with_variable](/blocks/system/all_with_variable)
- [block_foreach](/blocks/system/block_foreach)

---