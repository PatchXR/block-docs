# Tag Gate

**Category**: 🔗 Connectors

![selector_gate thumbnail](https://portal.patchxr.io/block-thumbnails/selector_gate.png)

## Description

Allows you to toggle a Tag connection on or off using a physical button or Jolt input.

When enabled, passes all Tag connections from the Input to the Output. When disabled, the Output is disconnected. The state can be controlled via the toggle button on the block or a Jolt input (0 = off, 1 = on).

## Related Wiki Pages

[dynamic-patching](/patching/dynamic-patching)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Tag Input |  |
| Toggle | Jolt Input | Toggle the connection On or Off depending on if the value is 0 or 1. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Tag Output |  |

### Others

| Name | Type | Description |
|------|------|-------------|
| Toggle | Toggle Button | Toggle the connection On/Off. |

---