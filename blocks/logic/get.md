# Get

**Category**: 🧠 Logic

![get thumbnail](https://portal.patchxr.io/block-thumbnails/get.png)

## Description

Emits a jolt with the current stream input value when triggered. Use it to snapshot a continuous stream value at a specific moment.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Value | Stream Input | The stream value that will be emitted on the next trigger (without firing the output by itself). |
| Trigger | Jolt Input | Send any jolt to make the block emit the current stream Value. The value of the incoming jolt is ignored. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the current Value as a jolt each time the block is triggered. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Button | Interactible | Click to send the current Value again. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Multiplayer Press | checkbox | When enabled (default), pressing the button fires the output for all players in the session. When disabled, only the local player's press fires the output (useful for actions like teleportation that should not affect everyone). |

## Related Blocks

- [stoe](/blocks/connectors/stoe)
- [constant](/blocks/logic/constant)
- [pass](/blocks/connectors/pass)
- [value](/blocks/interfaces/value)
- [operation](/blocks/logic/operation)

---