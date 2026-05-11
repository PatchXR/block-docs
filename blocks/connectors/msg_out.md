# OSC Send

**Category**: 🔗 Connectors

![msg_out thumbnail](https://portal.patchxr.io/block-thumbnails/msg_out.png)

## Description

Sends an OSC message every time the jolt input fires. Use :0 to insert the jolt value and :1, :2... for stream input values. Example: /ControllerHeight :0

Useful to drive external apps (DAWs, controllers, scripts) over the network from your patch. The text input defines the OSC address and arguments; placeholders :0 (jolt input), :1, :2, :3, :4 (stream inputs) are replaced with the current values when the message is sent. Use 'Number of additional arguments' in the inspector to add more inputs.

## Related Wiki Pages

[external-connections](/patching/external-connections)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Address | Text Input | OSC address and arguments to send. Use :0 for the jolt input value, :1..:4 for stream inputs. Example: /ControllerHeight :0 |
| Input :1 | Stream Input | Value from this input can be inserted in the message using :1 |
| Input :2 | Stream Input | Value from this input can be inserted in the message using :2 |
| Input :3 | Stream Input | Value from this input can be inserted in the message using :3 |
| Input :4 | Stream Input | Value from this input can be inserted in the message using :4 |
| Send Value (:0) | Jolt Input | Value from this jolt can be inserted in the message using :0 |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Number of additional arguments | integer | Number of extra jolt inputs (0-7) used to provide additional argument values that get appended to the OSC message. |
| Edit text from outside | checkbox | Allows the player to interact with the text input even when the block is inside a group/device. |

## Related Blocks

- [msg_in](/blocks/connectors/msg_in)
- [wireless_out_jolt](/blocks/connectors/wireless_out_jolt)
- [midi_control_change](/blocks/connectors/midi_control_change)
- [execute](/blocks/system/execute)

---