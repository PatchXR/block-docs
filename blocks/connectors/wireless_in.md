# Send Stream

**Category**: 🔗 Connectors

![wireless_in thumbnail](https://portal.patchxr.io/block-thumbnails/wireless_in.png)

## Description

Sends an audio stream wirelessly to every 'Receive Stream' (wireless_out) block sharing the same connection name. Avoids long cables across the patch.

All senders with the same name are summed together before being delivered to matching receivers. Use the Channel ID to split a single name into numbered sub-channels: a receiver only reads from senders whose Channel ID matches; using channel 0 acts as a wildcard that sends to / receives from every channel. The 'Send Data' inspector dropdown limits the reach of the broadcast: 'Across World' (default, anywhere in the world), 'Only in group' (restricts to the parent group/device), or 'To Selected Groups' (only the groups you connect via the tag selector).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Connection name | Text Input | Identifier of the wireless channel. Must match the connection name on the corresponding Receive Stream block. |
| Input | Stream Input | Stream to be sent. |
| Channel ID | Jolt Input with Dial | Sub-channel within the connection name. Set to 0 to send to every channel (wildcard), otherwise only receivers with the same Channel ID will pick up the signal. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Send Data | dropdown | Scope of the broadcast. 'Across World': reach every matching receiver in the world. 'Only in group': restrict the signal to the group/device this block lives in. 'To Selected Groups': only reach the groups connected to this block's tag selector. |
| Edit text from outside | checkbox | Allows the connection-name text input to be clicked and edited from outside the group/device this block belongs to. |

## Related Blocks

- [wireless_out](/blocks/connectors/wireless_out)
- [wireless_in_jolt](/blocks/connectors/wireless_in_jolt)
- [wireless_out_jolt](/blocks/connectors/wireless_out_jolt)
- [msg_in](/blocks/connectors/msg_in)
- [msg_out](/blocks/connectors/msg_out)

---