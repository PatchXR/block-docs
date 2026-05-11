# Midi CC

**Category**: 🔗 Connectors

![midi_control_change thumbnail](https://portal.patchxr.io/block-thumbnails/midi_control_change.png)

## Description

Bridges a single MIDI Control Change (CC) message between Patchworld and an external MIDI app (e.g. a DAW). Sends a CC out when the input fires, and emits a jolt when a matching CC is received.

Pick the MIDI channel (1-16) and control number (0-127) in the inspector. A jolt sent to the input is forwarded as a CC value (0-127) on that channel/control to the MIDI bridge. Conversely, when the host sends a CC matching the configured channel and control, the value is emitted on the output.

## Related Wiki Pages

[external-connections](/patching/external-connections)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Send CC value | Jolt Input | Jolt value (0-127) sent as the MIDI CC value on the configured channel and control. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Received CC value | Jolt Output | Emits a jolt carrying the value (0-127) of an incoming MIDI CC matching the configured channel and control. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Midi channel | integer | MIDI channel to send/receive on (1-16). |
| Midi control value | integer | MIDI CC number to bridge (0-127). Only CC messages with this number are received; outgoing messages use it as well. |

## Related Blocks

- [midi_key](/blocks/connectors/midi_key)
- [midi_keys](/blocks/connectors/midi_keys)
- [mic](/blocks/controllers/mic)
- [msg_in](/blocks/connectors/msg_in)
- [msg_out](/blocks/connectors/msg_out)

---