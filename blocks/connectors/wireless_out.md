# Receive Stream

**Category**: 🔗 Connectors

![wireless_out thumbnail](https://portal.patchxr.io/block-thumbnails/wireless_out.png)

## Description

Receives the audio stream broadcast by every 'Send Stream' (wireless_in) block sharing the same connection name. All matching senders are summed before reaching this output.

Use the Channel ID to filter incoming streams: only senders with a matching Channel ID will be heard. Setting Channel ID to 0 acts as a wildcard and receives from every channel under this connection name. Multiple receivers can share the same connection name to read the same mixed signal in different places of the patch.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Connection name | Text Input | Identifier of the wireless channel. Must match the connection name on the corresponding Send Stream block(s). |
| Channel ID | Jolt Input with Dial | Sub-channel to listen on. Set to 0 to receive from every channel (wildcard), otherwise only senders with the same Channel ID will be heard. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Edit text from outside | checkbox | Allows the connection-name text input to be clicked and edited from outside the group/device this block belongs to. |

## Related Blocks

- [wireless_in](/blocks/connectors/wireless_in)
- [wireless_in_jolt](/blocks/connectors/wireless_in_jolt)
- [wireless_out_jolt](/blocks/connectors/wireless_out_jolt)
- [msg_in](/blocks/connectors/msg_in)
- [msg_out](/blocks/connectors/msg_out)

---