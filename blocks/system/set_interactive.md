# Set Interactive

**Category**: ⚙️ System

![set_interactive thumbnail](https://portal.patchxr.io/block-thumbnails/set_interactive.png)

## Description

Enables or disables player interactivity on target blocks. When disabled, players cannot trigger, grab, or interact with the affected blocks. Send a jolt ≥ 0.5 to enable, < 0.5 to disable.

Also supports disabling individual player controllers when a Player block part is targeted (left hand, right hand, etc.). Works recursively on the contents of groups.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set Interactive | Jolt Input | Enables or disables interactivity on all target blocks. Send ≥ 0.5 to enable, < 0.5 to disable. |
| Add Target Block | Tag Input | Drag onto blocks to add them to the selection. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Target Blocks |  | The blocks whose interactivity is controlled by this block. |
| Interactive State | Toggle Button | Current interactivity state. Click to toggle on/off immediately. |

## Related Blocks

- [set_visible](/blocks/system/set_visible)
- [set_active](/blocks/system/set_active)
- [set_lock](/blocks/system/set_lock)

---