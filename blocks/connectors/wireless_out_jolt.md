# Send Jolt

**Category**: 🔗 Connectors

![wireless_out_jolt thumbnail](https://portal.patchxr.io/block-thumbnails/wireless_out_jolt.png)

## Description

Sends a jolt to every matching 'Receive Jolt' (wireless_in_jolt) block in the world without needing a wire. Pair sender and receiver by giving both the same channel name.

Useful for wiring large patches without long wires, or for sending jolts between separated groups/devices. Each wireless channel needs a unique name. Channel ID can be used to subdivide a name into multiple sub-channels (0 sends to all). The 'Send Data' inspector setting restricts where the jolt is delivered (world-wide, current group only, or a selected list of groups).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Jolt Input | Jolt to send wirelessly. The value is forwarded to every matching 'Receive Jolt' block on the same channel. |
| Connection name | Text Input | Name of the wireless channel. Must match the name typed on the corresponding 'Receive Jolt' (wireless_in_jolt) block. |
| Channel ID | Jolt Input with Dial | Optional sub-channel. Receivers with the same Channel ID get the jolt. Set to 0 to send on all channels sharing the connection name. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Send Data | dropdown | Restricts which receivers get the jolt. 'Across World' = all matching receivers anywhere. 'Only in group' = receivers inside the same parent group/device. 'To Selected Groups' = exposes a Tag input to pick specific groups/devices to target. |
| Broadcast Multiplayer | checkbox | When enabled, sent jolts are synced across multiplayer so remote players see the same event. |
| Edit text from outside | checkbox | Allows the player to interact with the text input even when the block is inside a group/device. |

## Related Blocks

- [wireless_in_jolt](/blocks/connectors/wireless_in_jolt)
- [wireless_in](/blocks/connectors/wireless_in)
- [wireless_out](/blocks/connectors/wireless_out)
- [msg_out](/blocks/connectors/msg_out)

---