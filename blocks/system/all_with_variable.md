# All With Variable

**Category**: ⚙️ System

![all_with_variable thumbnail](https://portal.patchxr.io/block-thumbnails/all_with_variable.png)

## Description

Output every block that has a given variable attached. Combine with "Block Foreach" to act on each result, or with the inspector to filter by value and sort the list.

This block scans the world (or a custom subset, if "Search From" is connected) for blocks tagged with the named variable via "Set Variable". It updates automatically as blocks are spawned, removed or change value, which makes it perfect for building dynamic gameplay (enemies, projectiles, pickups, scoreboards...) without having to wire each block manually.

The inspector exposes a "Value Filter" to keep only blocks whose variable equals a specific value, and an "Order in output" dropdown to sort the resulting list ascending or descending by value (e.g. to build a leaderboard).

See the [Variable System](/wiki/variable-system) wiki page for more details.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Variable Name | Text Input | Name of the variable to look for. Must match the name used by the corresponding "Set Variable". |
| Restrict (Optional) | Tag Input | Connect the same Group or Device used by "Set Variable" to find blocks tagged in this local scope. |
| Search From (Optional) | Tag Input | If connected: only blocks coming from this set are tested for the variable. If not connected: search across all blocks in the world. |
| Manual Trigger | Jolt Input | If connected: only re-evaluate the list when this jolt fires. If not connected: the list refreshes automatically whenever blocks are tagged, untagged or change value. |
| Value Filter (Optional) | Jolt Input with Dial | When enabled in the inspector, only blocks whose variable equals this value are kept in the output list. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Count | Jolt Output | Number of blocks currently in the output list. Re-emitted every time the list is recomputed. |
| Output | Tag Output | List of all blocks tagged with the variable. Connect to "Block Foreach" or to other Tag inputs. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Add restriction input | checkbox | Reveals the "Restrict" tag input. Required to find variables that were set with a matching restriction (i.e. local to a Group or Device). |
| Value Filter | checkbox | Reveals the "Value Filter" jolt+dial input. When enabled, only blocks whose variable equals this filter value are kept in the output list. |
| Order in output | dropdown | Sort the output list by the variable's value. "Ascending" puts the lowest value first; "Descending" puts the highest first. Useful for leaderboards or priority queues. |
| Edit text from outside | checkbox | When this block is placed inside a Group/Device, its text input is normally only editable from inside the group. Tick this option to let players still click and type into it from outside the group. |

## Related Blocks

- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)
- [remove_variable](/blocks/system/remove_variable)
- [block_foreach](/blocks/system/block_foreach)
- [block_compare](/blocks/system/block_compare)

---