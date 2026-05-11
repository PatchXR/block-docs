# Gate

**Category**: 🧠 Logic

![gate thumbnail](https://portal.patchxr.io/block-thumbnails/gate.png)

## Description

Allows or blocks jolts from passing through, based on the gate state. Open the gate by sending a stream value greater or equal to 0.5, or by clicking the toggle.

Use this block to enable or disable a signal flow conditionally, like an audio mute or an event filter that can be turned on or off dynamically.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Gate | Stream Input | Sets the gate state. Values equal or greater than 0.5 will set gate state to 'open'. |
| Input | Jolt Input | Receives jolt value which will be passed to the output if gate value is equal or greater than 0.5 |
| Close Gate | Jolt Input | Receiving a jolt here closes the gate (sets it to 0), blocking further input until reopened. |
| Open Gate | Jolt Input | Receiving a jolt here opens the gate (sets it to 1), allowing input jolts to pass through. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the received jolt value as a jolt if gate value is equal or greater than 0.5 |

### Others

| Name | Type | Description |
|------|------|-------------|
| Toggle | Toggle | Click to manually open or close the gate. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Interaction Type | dropdown | Controls how the toggle responds: Trigger (on trigger press), Touch (on contact), or None. |
| Momentary | checkbox | When enabled, the gate only stays open while the toggle is held. When disabled, it latches on click. |
| Allowed Touch Direction | dropdown | Limits which side of the toggle responds to touch: Front only, or Any direction. |

## Related Blocks

- sequence (link not available)
- [route](/blocks/logic/route)
- [if_else](/blocks/logic/if_else)
- [selector_gate](/blocks/connectors/selector_gate)

---