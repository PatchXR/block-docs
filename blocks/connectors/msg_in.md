# OSC Receive

**Category**: 🔗 Connectors

![msg_in thumbnail](https://portal.patchxr.io/block-thumbnails/msg_in.png)

## Description

Receives an OSC message at the specified address and emits its value as a jolt. Lets external apps (DAWs, controllers, scripts) drive your patch over the network.

Listens for OSC messages sent to the address typed in the text input (e.g. /my_address). When a matching message arrives, the value is emitted on the jolt output. Use the inspector to set how many additional jolt outputs to spawn for messages carrying multiple arguments.

## Related Wiki Pages

[external-connections](/patching/external-connections)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Address | Text Input | OSC address to listen on (e.g. /my_address). Must match the address used by the sender. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits a jolt carrying the value received from the OSC message. Additional outputs are added when 'Number of arguments' is increased in the inspector. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Broadcast jolt | checkbox | When enabled, the received jolt is also broadcast across multiplayer so remote players see the same event. |
| Number of arguments | integer | Number of jolt outputs (1-8). Use this when the incoming OSC message carries multiple values: each argument is emitted on its own output. |
| Edit text from outside | checkbox | Allows the player to interact with the text input even when the block is inside a group/device. |

## Related Blocks

- [msg_out](/blocks/connectors/msg_out)
- [wireless_in_jolt](/blocks/connectors/wireless_in_jolt)
- [midi_control_change](/blocks/connectors/midi_control_change)

---