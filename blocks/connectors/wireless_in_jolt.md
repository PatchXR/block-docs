# Receive Jolt

**Category**: 🔗 Connectors

![wireless_in_jolt thumbnail](https://portal.patchxr.io/block-thumbnails/wireless_in_jolt.png)

## Description

Receives jolts sent from matching 'Send Jolt' (wireless_out_jolt) blocks anywhere in the world, without needing a wire. Pair them by giving both blocks the same channel name.

Useful for wiring large patches without cluttering them with long wires, or for sending jolts between separated groups/devices. Each wireless channel needs a unique name. Channel ID can be used to subdivide a name into multiple sub-channels (0 receives from all).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Connection name | Text Input | Name of the wireless channel. Must match the name typed on the corresponding 'Send Jolt' (wireless_out_jolt) block. |
| Channel ID | Jolt Input with Dial | Optional sub-channel. Receives only jolts sent on the same Channel ID. Set to 0 to receive from all channels sharing the connection name. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits each jolt received on the matching channel. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Edit text from outside | checkbox | Allows the player to interact with the text input even when the block is inside a group/device. |

## Related Blocks

- [wireless_out_jolt](/blocks/connectors/wireless_out_jolt)
- [wireless_in](/blocks/connectors/wireless_in)
- [wireless_out](/blocks/connectors/wireless_out)
- [msg_in](/blocks/connectors/msg_in)

---