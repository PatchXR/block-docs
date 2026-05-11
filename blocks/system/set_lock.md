# Set Lock

**Category**: ⚙️ System

![set_lock thumbnail](https://portal.patchxr.io/block-thumbnails/set_lock.png)

## Description

Locks or unlocks the position of target blocks, preventing players from moving them. Send a jolt ≥ 0.5 to lock, < 0.5 to unlock.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set Lock | Jolt Input | Locks or unlocks all target blocks. Send ≥ 0.5 to lock, < 0.5 to unlock. |
| Add Target Block | Tag Input | Drag onto blocks to add them to the selection. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Lock State | Toggle Button | Current lock state. Click to toggle locked/unlocked immediately. |

## Related Blocks

- [set_visible](/blocks/system/set_visible)
- [set_active](/blocks/system/set_active)
- [set_interactive](/blocks/system/set_interactive)

---