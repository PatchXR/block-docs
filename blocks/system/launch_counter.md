# Load Counter

**Category**: ⚙️ System

![launch_counter thumbnail](https://portal.patchxr.io/block-thumbnails/launch_counter.png)

## Description

Fires a jolt carrying the number of times the local user has loaded this world. The count is output automatically on load, increments each visit, and is stored per user. The first visit is count 0.

The counter value is stored locally per user. It fires automatically when the world loads, but can also be retriggered at any time via the Get Count jolt input or by clicking the display button. Useful for triggering first-visit tutorials, tracking engagement, or unlocking content over repeated plays.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Get Count | Jolt Input | Triggers the Out output with the current visit count value. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Out | Jolt Output | Fires the visit count value. Triggered automatically on world load, and whenever Get Count is jolted. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Count Display | Interactible | Shows the current visit count. Click to manually fire the current count to the Out output. |

## Related Blocks

- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)
- [post_variable](/blocks/system/post_variable)
- [fetch_variable](/blocks/system/fetch_variable)

---